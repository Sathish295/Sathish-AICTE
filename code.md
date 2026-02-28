from PyQt5 import QtCore, QtGui, QtWidgets from Admin import Ui_Admin
import pandas as pd class Ui_Dialog(object): def admin(self, event):
try: self.admn = QtWidgets.QDialog() self.ui = Ui_Admin(self.admn)
self.ui.setupUi(self.admn) self.admn.show() except Exception as e:
print(e.args\[0\]) tb = sys.exc_info()\[2\] print(tb.tb_lineno)
event.accept()

def setupUi(self, Dialog): Dialog.setObjectName(\"Dialog\")
Dialog.resize(702, 435) Dialog.setStyleSheet(\"background-color: rgb(0,
85, 127);\") self.label = QtWidgets.QLabel(Dialog)
self.label.setGeometry(QtCore.QRect(60, 60, 601, 41))
self.label.setStyleSheet(\"color: rgb(255, 255, 255);\\n\" \"font: 75
18pt \\\"Tahoma\\\";\") self.label.setObjectName(\"label\") self.label_2
= QtWidgets.QLabel(Dialog) self.label_2.setGeometry(QtCore.QRect(200,
150, 261, 181))

self.label_2.setStyleSheet(\"image: url(../N-Grams/images/admin.png);\")
self.label_2.setText(\"\") self.label_2.setObjectName(\"label_2\")
self.label_2.mousePressEvent = self.admin

self.retranslateUi(Dialog) QtCore.QMetaObject.connectSlotsByName(Dialog)

def retranslateUi(self, Dialog): \_translate =
QtCore.QCoreApplication.translate
Dialog.setWindowTitle(\_translate(\"Dialog\", \"Online Fake News\"))
self.label.setText(\_translate(\"Dialog\", \"Detection of Online Fake
News Using N- Gram Analysis\"))

if \_name\_ == \"\_main\_\": import sys app =
QtWidgets.QApplication(sys.argv) Dialog = QtWidgets.QDialog() ui =
Ui_Dialog() ui.setupUi(Dialog) Dialog.show() sys.exit(app.exec\_())
