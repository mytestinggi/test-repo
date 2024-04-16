#import the necessary modules
import smtplib, ssl, csv
from email.message import EmailMessage

sender = 'your email'
password = 'app password'

subject = 'add the subject'
body_message = 'type the message'

#connect to our outgoing mail SMTP server
context = ssl.create_default_context()
server = smtplib.SMTP_SSL('smtp.gmail.com', 465, context = context)

server.login(sender, password)

#The formula we will use to send emails
with open('csv file path','r') as csvfile:
     datareader = csv.reader(csvfile)
     for row in datareader:
         em = EmailMessage()
         em['From'] = sender
         em['To'] = row
         em['Subject'] = subject
         em.set_content(body_message)
         server.send_message(em)
         print("The message sent")

server.closed()
