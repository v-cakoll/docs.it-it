---
title: 'Procedura: scrivere le impostazioni utente in fase di esecuzione con C#'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5966aef77c994d2657bd282ad15e8f59a64eeb47
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a>Procedura: scrivere le impostazioni utente in fase di esecuzione con C# #
Le impostazioni con ambito di applicazione sono di sola lettura e possono essere modificate solo in fase di progettazione o modificando il file .config tra sessioni dell'applicazione. Le impostazioni con ambito di utente possono invece essere scritte in fase di esecuzione usando la stessa procedura adottata per modificare il valore di una proprietà. Il nuovo valore viene mantenuto per la durata della sessione dell'applicazione. È possibile mantenere le modifiche alle impostazioni tra le sessioni dell'applicazione chiamando il metodo Save.  
  
### <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a>Procedura: Scrivere e mantenere le impostazioni utente in fase di esecuzione con C#  
  
1.  Accedere all'impostazione e assegnarle un nuovo valore come mostrato nell'esempio seguente:  
  
    ```  
    // C#  
    Properties.Settings.Default.myColor = Color.AliceBlue;  
    ```  
  
2.  Se si vogliono mantenere le modifiche alle impostazioni tra sessioni dell'applicazione, chiamare il metodo Save, come mostrato nell'esempio seguente:  
  
    ```  
    // C#  
    Properties.Settings.Default.Save();  
    ```  
  
     Le impostazioni utente vengono salvate in un file all'interno di una sottocartella della cartella dati applicazioni nascosta locale dell'utente.  
  
## <a name="see-also"></a>Vedere anche  
 [Uso delle impostazioni applicazione e delle impostazioni utente](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [Procedura: Leggere le impostazioni in fase di esecuzione con C#](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)  
 [Cenni preliminari sulle impostazioni delle applicazioni](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
