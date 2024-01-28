yazdığın uygulamayı pcde çalışırmak için aşamalar
Aşama 1
    pip install pyinstaller
Aşama 2
    pip freeze
Aşama 3 (dosyayı tanımlar
        def loadStyles(self):
        try:
            # Executable'ın bulunduğu dizini bul
            base_path = getattr(sys, '_MEIPASS', os.path.dirname(os.path.abspath(__file__)))

            # style.qss dosyasının yolunu oluştur
            style_file_path = os.path.join(base_path, "style.qss")

            # Dosyayı aç ve içeriğini oku
            with open(style_file_path, "r") as stylefile:
                self.setStyleSheet(stylefile.read())  # Apply the stylesheet to the app
        except Exception as e:
            print(f"Error loading style.qss: {e}")
Aşama 4
        pyinstaller --onefile --windowed --add-data "style.qss;." main.py

