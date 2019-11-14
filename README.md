# ClassGestionnaire
# -*- coding: utf-8 -*-
"""
Created on Mon Nov 11 18:50:37 2019

@author: MOHAMADOU Mouctar
"""
class Gestionnaire() :
    
    def __init__(self, nom, id, montant):
        self.nom = nom
        self.id = id
        self.montant = montant
        
    def enregistre_emprunt(self, montant):
        reponse = input("avez-vous d'emprunt à rembourser ? oui/non \n")
        if reponse == "non" :
            print("vous pouvez obtenir d'emprunt")
            montant =  int(input("veuillez entrer le montant avec taux de 10% d'emprunt "))
            print("vous aller emprunter un montant de ",montant, "fcfa \n Veillez passer au Guichetier pour finaliser l'óperation")
        elif reponse == "oui" :
            print("vous ne pouvez pas obtenir d'emprunt")
        else :
            print("saisi incorrect")
        
    def enregistre_gestion(self, ajouts, modifier, suppressions):
        gestion = input("veuillez faire votre choix de  \n 1. ajouts \n 2. suppressions \n 3. modification \n")
        if gestion == "1":
            compte = input("veuillez faire votre choix du compte \n 1. compte_Epargne \n 2. compte_Courant \n 3. compte_GreàGre \n")
            if compte == "1" :
                print("vous venez d'ajouter compte_Epargne")
            elif compte == "2" :
                print("vous venez d'ajouter compte_Courant")
            elif compte == "3" :
                print("vous venez d'ajouter compte_GreàGre")
            else :
                print("saisi incorrect")
        elif gestion == "2":
            compte = input("veuillez faire votre choix du compte \n 1. compte_Epargne \n 2. compte_Courant \n 3. compte_GreàGre \n")
            if compte == "1" :
                print("vous venez de supprimer compte_Epargne")
            elif compte == "2" :
                print("vous venez de supprimer compte_Courant")
            elif compte == "3" :
                print("vous venez de supprimer compte_GreàGre")
            else :
                print("saisi incorrect")
        elif gestion == "3":
            compte = input("veuillez faire votre choix du compte \n 1. compte_Epargne \n 2. compte_Courant \n 3. compte_GreàGre \n")
            if compte == "1" :
                print("vous venez de modifier compte_Epargne")
            elif compte == "2" :
                print("vous venez de modifier compte_Courant")
            elif compte == "3" :
                print("vous venez de modifier compte_GreàGre")
            else :
                print("saisi incorrect")
        else :
            print("saisi incorrect")
            
        
# Programme Principale 

            
Client_Banque = {}
Reponse_Client = True

while Reponse_Client :
        nom = input("Quel est le nom du client: ")
        idcode = input("Quel est le idcode du client: ")
        solde = input("Quel est le solde actuel du compte: " )
        
        print("\n")
        print("Bienvenue ",nom ,idcode, "fcfa avec un solde initial de",solde, "fcfa")
        
        choix_opperation = input("Faite votre choix d'opperation \n 1. enregistre_emprunt; \n 2. gestion_compte \n")
        ajouts = "nul"
        montant = "nul"
        suppressions = "nul"
        if choix_opperation == "1" :
            client1 = Gestionnaire(nom, idcode, montant)
            client1.enregistre_emprunt(montant)
        elif choix_opperation == "2" :
            client1 = Gestionnaire(nom, idcode, montant)
            client1.enregistre_gestion(ajouts, montant,suppressions)
        else :
           print("commande invalide") 
            
        reponse = input("Voulez-vous continuer avec un autre client? oui/non\n")
        if reponse == "oui" :
            continue
        else:
            print("Au revoir", nom, idcode)
            Reponse_Client = False
