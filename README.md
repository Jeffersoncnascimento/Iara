# Iara
# Inteligencia Artificial Totalmente Feito em Python 
Tela de Login:
#Bibliotecas Ultilizadas
import tkinter
import customtkinter #Parte da Interface
from tkinter import RIGHT, PhotoImage, messagebox
from PIL import Image, ImageTk
import os
import subprocess
from sys import platform

#Abrindo a Janela de login
customtkinter.set_appearance_mode("dark")
customtkinter.set_default_color_theme("dark-blue")

janela = customtkinter.CTk() 
janela.geometry("700x400")
janela.title("Sistema de Login")
#icone 
janela.iconbitmap("icon.ico")
janela.resizable(False, False) #para deixar a janela sem ajuste
#imagem Logo
img = PhotoImage(file="imglogo.png")
label_img = customtkinter.CTkLabel(master=janela, image=img, text="")
label_img.place(x=30, y=90)

#########################################################################################################################################
#Titulo
label_tt = customtkinter.CTkLabel(master=janela, text="Entre em sua Conta", font=("Roboto", 30), text_color="#00B0F0").place(x=45, y=30)
#########################################################################################################################################

#Frame
frame = customtkinter.CTkFrame(master=janela, width=350, height=396)
frame.pack(side=RIGHT)

#Frame wigdgets
label = customtkinter.CTkLabel(master= frame, text= "Sistema de Login", font=("Roboto", 30)) #se for mudar a cor colocar ,text_color ="cor"
label.place(x=50, y=40)

entry1 = customtkinter.CTkEntry(master=frame, placeholder_text="Nome do Usuario", width=300,font=("Roboto", 14)).place(x=25, y=120)
entry2 = customtkinter.CTkEntry(master=frame, placeholder_text="Senha do Usuario", width=300,font=("Roboto", 14), show="*").place(x=25, y=170)

def button_esqueceu():
    #Remover o Freme do login
    frame.pack_forget()
    #Tela de cadastro
    rg_frame = customtkinter.CTkFrame(master=janela, width=350, height=396)
    rg_frame.pack(side=RIGHT)
    label = customtkinter.CTkLabel(master= rg_frame, text= "Esqueceu sua Senha?", font=("Roboto", 30)) #se for mudar a cor colocar ,text_color ="cor"
    label.place(x=40, y=50)

    span = customtkinter.CTkLabel(master=rg_frame, text= "Você esqueceu sua senha? pode ficar tranquilo!\n insira seu e-mail abaixo, será enviado um \nE-mail para Redefinição de Senha.", font=("Roboto",15),text_color="grey").place(x=10, y=100)

    #Entradas:
    entry1 = customtkinter.CTkEntry(master=rg_frame, placeholder_text="Insira seu E-mail", width=300,font=("Roboto", 14)).place(x=25, y=180)
    #Botões:
    def back():

        #removendo o frame de cadastro 
        rg_frame.pack_forget()

        #Devolvendo o Freme do login
        frame.pack(side=RIGHT)

    back_button = customtkinter.CTkButton(master=rg_frame, text="Voltar", width=145, fg_color="gray",hover_color="#202020", command=back).place(x=25, y=250)
    def save_user():
        msg = messagebox.showinfo(title="Redefinição de Senha", message="Enviado uma confirmação de redefinição de senha, para o E-mail informado!")
    save_button = customtkinter.CTkButton(master=rg_frame, text="Enviar", width=145, fg_color="green",hover_color="#014B05",command=save_user).place(x=180, y=250)
    
    pass
pass
button_esqueceu = customtkinter.CTkButton(master=frame, text="Esqueceu sua Senha?", width=20,height=15, fg_color="grey21", hover_color= "#363636", command= button_esqueceu).place(x=25, y=210)

checkbox = customtkinter.CTkCheckBox(master=frame, text= "Lembre-se de mim").place(x= 25, y=245)

def menu_principal():

    #Caminho para o Programa
    subprocess.call("python Tela_Menu.py")
    
pass
button = customtkinter.CTkButton(master=frame, text="Login", width=300, command=menu_principal).place(x=25, y=285)

register_span = customtkinter.CTkLabel(master= frame, text="Não tem uma conta?\nfaça uma agora mesmo").place(x=25, y=325)

def tela_cadastro():
    #Remover o Freme do login
    frame.pack_forget()
    #Tela de cadastro
    rg_frame = customtkinter.CTkFrame(master=janela, width=350, height=396)
    rg_frame.pack(side=RIGHT)
    label = customtkinter.CTkLabel(master= rg_frame, text= "Faça o seu Cadastro:", font=("Roboto", 30)) #se for mudar a cor colocar ,text_color ="cor"
    label.place(x=40, y=20)
    span = customtkinter.CTkLabel(master=rg_frame, text= "Preencha todos os campos com os dados corretos!\nVocê irá utilizar para o Login: *Nome de Usuario e Senha*", font=("Roboto",12),text_color="grey").place(x=25, y=60)
    #Entradas:
    entry1 = customtkinter.CTkEntry(master=rg_frame, placeholder_text="Nome do Usuario", width=300,font=("Roboto", 14)).place(x=25, y=105)
    entry2 = customtkinter.CTkEntry(master=rg_frame, placeholder_text="E-mail do Usuario", width=300,font=("Roboto", 14)).place(x=25, y=145)
    entry3 = customtkinter.CTkEntry(master=rg_frame, placeholder_text="Número de Telefone", width=300,font=("Roboto", 14)).place(x=25, y=185)
    entry4 = customtkinter.CTkEntry(master=rg_frame, placeholder_text="Senha", width=300,font=("Roboto", 14),show="*").place(x=25, y=225)
    #Check BOX
    checkbox = customtkinter.CTkCheckBox(master=rg_frame, text= "Aceitar todos os termos de uso").place(x= 25, y=270)
    
    #Botões:
    def back():

        #removendo o frame de cadastro 
        rg_frame.pack_forget()

        #Devolvendo o Freme do login
        frame.pack(side=RIGHT)

    back_button = customtkinter.CTkButton(master=rg_frame, text="Voltar", width=145, fg_color="gray",hover_color="#202020", command=back).place(x=25, y=315)
    def save_user():
        msg = messagebox.showinfo(title="Estado do Cadastro", message="Parabens! Usuario cadastrado com sucesso.")
    save_button = customtkinter.CTkButton(master=rg_frame, text="Cadastrar", width=145, fg_color="green",hover_color="#014B05",command=save_user).place(x=180, y=315)
    
    
    pass
button = customtkinter.CTkButton(master= frame, text="Cadastre-se", width=150, fg_color="green", hover_color= "#2D9334", command=tela_cadastro).place(x=175,y=325)

janela.mainloop()

