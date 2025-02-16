# CHATAI-YOU-AI
import random
import time

class CHATAI:
    def __init__(self, name="CHATAI"):
        self.name = name
        # Hier definieren wir mögliche Fragen und Antworten
        self.responses = {
            "hallo": ["Hallo! Wie kann ich dir helfen?", "Hi! Was kann ich für dich tun?", "Hallo! Wie geht's dir?"],
            "wie geht's": ["Mir geht's gut, danke der Nachfrage! Und dir?", "Ich bin bereit, dir zu helfen! Wie geht's dir?", "Alles bestens, danke! Wie geht es dir?"],
            "hilfe": ["Ich bin hier, um dir zu helfen! Was möchtest du wissen?", "Ich stehe zur Verfügung, was möchtest du lernen?", "Was brauchst du? Ich bin für dich da!"],
            "was ist dein name": ["Mein Name ist CHATAI, dein virtueller Assistent!", "Ich bin CHATAI, dein persönlicher Helfer!", "Ich bin CHATAI, wie kann ich dir helfen?"],
            "wie alt bist du": ["Ich bin ein Programm, also habe ich kein Alter. Aber ich bin immer bereit, dir zu helfen!", "Alter? Ich bin immer jung, als KI habe ich keine Zeit!", "Ich habe kein Alter, aber ich bin immer bereit, dir zu helfen!"],
            "was ist die bedeutung des lebens": ["Die Bedeutung des Lebens? Das ist eine philosophische Frage! Viele sagen, es geht darum, glücklich zu sein.", "Die Bedeutung des Lebens ist vielleicht, nach Wissen zu streben und sich weiterzuentwickeln!", "Es gibt viele Antworten darauf, aber vielleicht ist es, Liebe und Freude zu teilen."],
            "bye": ["Tschüss! Bis zum nächsten Mal!", "Auf Wiedersehen, pass gut auf dich auf!", "Tschüss, es war schön mit dir zu sprechen!"]
        }

    # Begrüßung
    def greet(self):
        print(f"{self.name}: Hallo! Ich bin {self.name}, dein virtueller Assistent. Wie kann ich dir helfen?")

    # Antwort basierend auf Benutzeranfragen
    def get_response(self, user_input):
        user_input = user_input.lower()  # Eingabe in Kleinbuchstaben umwandeln
        
        # Suche nach passenden Antworten
        for key in self.responses:
            if key in user_input:
                return random.choice(self.responses[key])
        
        # Wenn keine passende Antwort gefunden wird, gib eine Standardantwort
        return "Entschuldigung, das habe ich nicht verstanden. Kannst du das anders formulieren?"

    # Chat mit dem Benutzer
    def chat(self):
        self.greet()
        
        while True:
            user_input = input("Du: ")
            if "bye" in user_input.lower():
                print(f"{self.name}: {self.get_response('bye')}")
                break
            response = self.get_response(user_input)
            print(f"{self.name}: {response}")
            time.sleep(1)  # Eine kurze Verzögerung für die Realitätsnähe

# Hauptprogramm
if __name__ == "__main__":
    chat_ai = CHATAI()
    chat_ai.chat()
