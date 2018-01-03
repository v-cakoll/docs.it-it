---
title: Sviluppo rapido di applicazioni con My.Resources e My.Settings (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7339afdc35341739b592b2a327094754031c346c
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>Sviluppo rapido di applicazioni con My.Resources e My.Settings (Visual Basic)
Il `My.Resources` oggetto fornisce l'accesso alle risorse dell'applicazione e consente di recuperare in modo dinamico le risorse per l'applicazione.  
  
## <a name="retrieving-resources"></a>Recupero di risorse  
 Un numero di risorse, ad esempio file audio, icone, immagini e stringhe può essere recuperato tramite il `My.Resources` oggetto. Ad esempio, è possibile accedere il file di risorse specifiche delle impostazioni cultura dell'applicazione. Nell'esempio seguente imposta l'icona del form per l'icona denominato `Form1Icon` archiviati nel file di risorse dell'applicazione.  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 Il `My.Resources` oggetto espone solo le risorse globali. Non fornisce accesso ai file di risorse associato al form. È necessario accedere alle risorse di modulo dal modulo.  
  
 Analogamente, il `My.Settings` oggetto fornisce accesso alle impostazioni dell'applicazione e consente di archiviare e recuperare le impostazioni delle proprietà e altre informazioni per l'applicazione in modo dinamico. Per ulteriori informazioni, vedere [oggetto My. Resources](../../../visual-basic/language-reference/objects/my-resources-object.md) e [oggetto My. Settings](../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Oggetto My.Resources](../../../visual-basic/language-reference/objects/my-resources-object.md)  
 [Oggetto My.Settings](../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [Accesso alle impostazioni dell'applicazione](../../../visual-basic/developing-apps/programming/app-settings/accessing-application-settings.md)
