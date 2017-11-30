---
title: "Procedura: aggiungere più set di impostazioni all'applicazione in C#"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ec541a8f83990eec79226be7fb4880ef8dda639d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a>Procedura: aggiungere più set di impostazioni all'applicazione in C# #
In alcuni casi, è possibile disporre di più set di impostazioni in un'applicazione. Ad esempio, se si sviluppa un'applicazione in un determinato gruppo di impostazioni deve modificati di frequente, potrebbe essere opportuno separare tutti in un singolo file in modo che il file può essere sostituito a livello globale, lasciando immutati altre impostazioni. Visual Studio consente di aggiungere più set di impostazioni per il progetto. Altri set di impostazioni sono accessibili tramite l'oggetto Properties. Settings.  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a>Per aggiungere un altro Set di impostazione dell'applicazione  
  
1.  Dal menu **Progetto**, scegliere **Aggiungi nuovo elemento**. Viene aperta la finestra di dialogo **Aggiungi nuovo elemento**.  
  
2.  Nel **Aggiungi nuovo elemento** nella finestra di dialogo **File di impostazioni**, digitare un nome per il file e fare clic su **Aggiungi** per aggiungere un nuovo file di impostazioni per la soluzione.  
  
3.  In **Esplora**, trascinare il nuovo file di impostazioni nel **proprietà** cartella. In questo modo le nuove impostazioni siano disponibili nel codice.  
  
4.  Aggiungere e utilizzare le impostazioni in questo file come per qualsiasi altro file di impostazioni. È possibile accedere a questo gruppo di impostazioni tramite l'oggetto Properties. Settings.  
  
## <a name="see-also"></a>Vedere anche  
 [Uso delle impostazioni applicazione e delle impostazioni utente](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [Cenni preliminari sulle impostazioni delle applicazioni](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
