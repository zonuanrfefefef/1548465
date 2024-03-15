# 1548465
隨機檔案名生成 可自選附檔名   (參考)    
import tkinter as tk
import random
import string

class FileNameGenerator:
    def __init__(self, master):
        self.master = master
        self.master.title("隨機檔案名生成器")

        self.extension_entry = tk.Entry(master)
        self.generate_button = tk.Button(master, text="生成", command=self.generate_filename)
        self.result_label = tk.Label(master, text="")

        self.extension_entry.pack()
        self.generate_button.pack()
        self.result_label.pack()

    def generate_filename(self):
        extension = self.extension_entry.get()
        filename = ''.join(random.choice(string.ascii_letters + string.digits) for _ in range(10)) + '.' + extension
        self.result_label.config(text=filename)

root = tk.Tk()
my_generator = FileNameGenerator(root)
root.mainloop()
