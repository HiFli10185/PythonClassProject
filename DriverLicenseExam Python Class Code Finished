def storeStudentAnswersInFile(fileName, correctAnswersList):
    studentAnswersFile = open(fileName, "w")
    numberOfQuestions = len(correctAnswersList)

    for currentUserAnswerIndex in range(numberOfQuestions):
        userAnswer = input("Please enter the answer for question " +
                           str(currentUserAnswerIndex + 1) + ": ")
        studentAnswersFile.write(userAnswer + "\n")

    studentAnswersFile.close()


def readStudentAnswersFromFileToList(fileName):
    studentAnswersList = []
    studentAnswersFile = open(fileName, "r")

    for studentAnswer in studentAnswersFile:
        studentAnswersList.append(studentAnswer.strip())

    studentAnswersFile.close()
    return studentAnswersList


def determineNumberOfCorrectAnswers(examCorrectAnswersList, studentCorrectAnswersList):
    correctAnswers = 0
    numberOfQuestions = len(examCorrectAnswersList)

    for currentExamQuestionIndex in range(numberOfQuestions):
        if studentCorrectAnswersList[currentExamQuestionIndex] == examCorrectAnswersList[currentExamQuestionIndex]:
            correctAnswers += 1

    return correctAnswers


def determineNumberOfIncorrectAnswers(numberOfCorrectAnswers, numberOfQuestions):
    numberOfIncorrectAnswers = numberOfQuestions - numberOfCorrectAnswers
    return numberOfIncorrectAnswers


def getIncorrectlyAnsweredQuestionNumbers(examCorrectAnswersList, studentCorrectAnswersList):
    incorrectQuestionNumbersList = []
    numberOfQuestions = len(examCorrectAnswersList)

    for currentExamQuestionIndex in range(numberOfQuestions):
        if studentCorrectAnswersList[currentExamQuestionIndex] != examCorrectAnswersList[currentExamQuestionIndex]:
            incorrectQuestionNumbersList.append(currentExamQuestionIndex + 1)

    return incorrectQuestionNumbersList


def studentPassedExam(passMark, studentCorrectAnswersList):
    if len(studentCorrectAnswersList) >= passMark:
        return True
    else:
        return False


def printValuesInList(anyList):
    for currentValueIndex in range(len(anyList)):
        print(anyList[currentValueIndex])


def printResults(numberOfCorrectlyAnsweredQuestions, numberOfIncorrectlyAnsweredQuestions,
                 incorrectlyAnsweredQuestionNumbersList):
    print("Number of correctly answered questions:", numberOfCorrectlyAnsweredQuestions)
    print("Number of incorrectly answered questions:", numberOfIncorrectlyAnsweredQuestions)
    print("Incorrectly answered question numbers:", incorrectlyAnsweredQuestionNumbersList)


def main():
    correctAnswersList = ["A", "B", "C", "C", "A", "A", "A", "C", "D", "B",
                          "A", "D", "C", "A", "D", "C", "B", "D", "A"]

    NUMBER_OF_QUESTIONS = len(correctAnswersList)
    FILE_NAME = "studentAnswers.txt"
    PASS_MARK = 15

    storeStudentAnswersInFile(FILE_NAME, correctAnswersList)

    studentAnswersList = readStudentAnswersFromFileToList(FILE_NAME)

    numberOfCorrectAnswers = determineNumberOfCorrectAnswers(correctAnswersList, studentAnswersList)

    numberOfIncorrectAnswers = determineNumberOfIncorrectAnswers(numberOfCorrectAnswers, NUMBER_OF_QUESTIONS)

    incorrectQuestionNumbersList = getIncorrectlyAnsweredQuestionNumbers(correctAnswersList, studentAnswersList)

    printResults(numberOfCorrectAnswers, numberOfIncorrectAnswers, incorrectQuestionNumbersList)

    if studentPassedExam(PASS_MARK, studentAnswersList):
        print("The student passed the exam")
    else:
        print("The student failed the exam")


main()
