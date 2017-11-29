---
title: 'Procedura: eliminare una chiave del Registro di sistema in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.DeleteSetting
helpviewer_keywords:
- GetSetting function [Visual Basic]
- registry [Visual Basic], deleting values
- GetAllSettings function
- registry keys [Visual Basic], deleting
- registry [Visual Basic], deleting keys
- examples [Visual Basic], registry
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0cb98c02531bac133b9dc37a92f75d5c0418dc7c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-delete-a-registry-key-in-visual-basic"></a>Procedura: eliminare una chiave del Registro di sistema in Visual Basic
È possibile usare i metodi <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> e <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> per eliminare le chiavi del Registro di sistema.  
  
## <a name="procedure"></a>Routine  
  
#### <a name="to-delete-a-registry-key"></a>Per eliminare una chiave del Registro di sistema  
  
-   Usare il metodo `DeleteSubKey` per eliminare una chiave del Registro di sistema. Questo esempio elimina la chiave Software/TestApp nell'hive CurrentUser. È possibile impostarlo nel codice sulla stringa appropriata oppure basarsi sulle informazioni specificate dall'utente.  
  
     [!code-vb[VbResourceTasks#19](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-delete-a-registry-key_1.vb)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Il metodo `DeleteSubKey` restituisce una stringa vuota se la coppia chiave/valore non esiste.  
  
 Le seguenti condizioni possono generare un'eccezione:  
  
-   Il nome della chiave è `Nothing` (<xref:System.ArgumentNullException>).  
  
-   L'utente non è autorizzato a eliminare le chiavi del Registro di sistema (<xref:System.Security.SecurityException>).  
  
-   Il nome della chiave supera il limite di 255 caratteri (<xref:System.ArgumentException>).  
  
-   La chiave del Registro di sistema è di sola lettura (<xref:System.UnauthorizedAccessException>).  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Le chiamate al Registro di sistema hanno esito negativo se non sono concesse autorizzazioni sufficienti in fase di esecuzione (<xref:System.Security.Permissions.RegistryPermission>) o se, in base a quanto determinato dagli ACL, l'utente non usa l'accesso corretto per la creazione o la scrittura nelle impostazioni. Ad esempio, un'applicazione locale che ha l'autorizzazione di sicurezza dall'accesso di codice potrebbe non avere l'autorizzazione del sistema operativo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>  
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>  
 <xref:Microsoft.Win32.RegistryKey>  
 [Sicurezza e Registro di sistema](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)  
 [Lettura e scrittura nel Registro di sistema](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
