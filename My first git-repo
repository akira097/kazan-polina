from PyQt5 import QtCore, QtGui, QtWidgets
from PyQt5.QtGui import QPainter, QColor
from random import randint


class Ui_Form(object):
    def setupUi(self, Form):
        Form.setObjectName("Form")
        Form.resize(400, 300)
        self.pushButton = QtWidgets.QPushButton(Form)
        self.pushButton.setGeometry(QtCore.QRect(150, 120, 101, 51))
        self.pushButton.setObjectName("pushButton")

        self.pushButton.clicked.connect(self.add_circle)

        self.retranslateUi(Form)
        QtCore.QMetaObject.connectSlotsByName(Form)

    def retranslateUi(self, Form):
        _translate = QtCore.QCoreApplication.translate
        Form.setWindowTitle(_translate("Form", "Form"))
        self.pushButton.setText(_translate("Form", "Add Circle"))


class CircleWindow(QtWidgets.QMainWindow):
    def __init__(self):
        super().__init__()

        # Load the UI file
        self.ui = Ui_Form()
        self.ui.setupUi(self)

        self.circles = []

    def add_circle(self):
        # Add a random circle to the list
        diameter = randint(10, 100)
        self.circles.append((randint(0, 400), randint(0, 300), diameter))

        self.update()

    def paintEvent(self, event):
        painter = QPainter(self)
        for circle in self.circles:
            painter.setBrush(QColor("yellow"))
            painter.drawEllipse(circle[0] - circle[2]//2, circle[1] - circle[2]//2, circle[2], circle[2])


if __name__ == "__main__":
    import sys

    app = QtWidgets.QApplication(sys.argv)
    window = CircleWindow()
    window.show()
    sys.exit(app.exec_())
