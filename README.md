class Quiz:
    def __init__(self): # Fixed typo here
        self.questions = [
            {
                "question": "What is the capital of France?",
                "options": ["A) London", "B) Berlin", "C) Paris", "D) Madrid"],
                "answer": "C"
            },
            {
                "question": "What is 2 + 2?",
                "options": ["A) 3", "B) 4", "C) 5", "D) 6"],
                "answer": "B"
            },
            {
                "question": "What is the largest planet in our solar system?",
                "options": ["A) Earth", "B) Mars", "C) Saturn", "D) Jupiter"],
                "answer": "D"
            }
        ]
        self.score = 0

    def validate_input(self, user_input):
        if user_input.upper() in ['A', 'B', 'C', 'D']:
            return True
        else:
            return False

    def run_quiz(self):
        for i, q in enumerate(self.questions):
            print(f"Question {i+1}: {q['question']}")
            for option in q['options']:
                print(option)
            
            user_answer = input("Your answer (A, B, C, or D): ").upper()

            while not self.validate_input(user_answer):
                print("Invalid input. Please enter A, B, C, or D.")
                user_answer = input("Your answer (A, B, C, or D): ").upper()

            if user_answer == q['answer']:
                print("Correct!\n")
                self.score += 1
            else:
                print(f"Incorrect. The correct answer is {q['answer']}.\n")

        self.display_final_score()

    def display_final_score(self):
        print(f"You scored {self.score} out of {len(self.questions)}!")

if __name__ == "__main__": # Fixed typo here
    quiz = Quiz()
    quiz.run_quiz()
