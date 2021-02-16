# pass_pdf
Password for a PDF using Python
from PyPDF2 import PdfFileReader,PdfFileWriter
file_pdf=PdfFileReader('123.pdf')#read
out_pdf=PdfFileWriter()#object for pdf writer
file_pdf

for i in range(file_pdf.numPages):
    page_details=file_pdf.getPage(i)#add to the output page
    out_pdf.addPage(page_details)
    
password="qaz@123"
out_pdf.encrypt(password)

with open("encryptedtickets.pdf","wb") as filename:
    out_pdf.write(filename)
