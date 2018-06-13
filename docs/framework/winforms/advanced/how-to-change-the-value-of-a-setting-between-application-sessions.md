---
title: "Procedura: modificare il valore di un'impostazione tra le sessioni dell'applicazione"
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: 383f72f223fb92170d16a9538c94e67825009abb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523410"
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a>Procedura: modificare il valore di un'impostazione tra le sessioni dell'applicazione
In alcuni casi, si potrebbe voler modificare il valore di un'impostazione tra le sessioni dell'applicazione dopo aver compilato e distribuito l'applicazione. Potrebbe ad esempio, si desidera modificare una stringa di connessione in modo che punti al percorso del database corretto. Poiché gli strumenti di progettazione non sono disponibili dopo aver compilato e distribuito l'applicazione, è necessario modificare il valore dell'impostazione manualmente nel file.  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a>Per modificare il valore di un'impostazione tra le sessioni dell'applicazione  
  
1.  Utilizzando Microsoft Notepad o alcuni altri editor di testo o XML, aprire il file config associato all'applicazione.  
  
2.  Individuare la voce per l'impostazione che si desidera modificare. Sarà simile all'esempio riportati di seguito.  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  Digitare un nuovo valore per l'impostazione e salvare il file.  
  
## <a name="see-also"></a>Vedere anche  
 [Uso delle impostazioni applicazione e delle impostazioni utente](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [Cenni preliminari sulle impostazioni delle applicazioni](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
