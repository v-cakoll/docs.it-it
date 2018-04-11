---
title: Errore imprevisto. Impossibile acquisire una risorsa del sistema operativo necessaria per l'avvio di istanze singole
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrAppModel_CantGetMemoryMappedFile
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8969303d66e946d5579c6cca592b5701c4ebd632
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="an-unexpected-error-has-occurred-because-an-operating-system-resource-required-for-single-instance-startup-cannot-be-acquired"></a>Errore imprevisto. Impossibile acquisire una risorsa del sistema operativo necessaria per l'avvio di istanze singole
L'applicazione non è riuscita ad acquisire una risorsa del sistema operativo necessaria. Alcune possibili cause di questo problema sono:  
  
-   L'applicazione non dispone di autorizzazioni per la creazione di oggetti del sistema operativo denominati.  
  
-   Common Language Runtime non dispone di autorizzazioni per la creazione di file mappati alla memoria.  
  
-   L'applicazione deve accedere a un oggetto del sistema operativo, ma un altro processo lo sta usando.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Verificare che l'applicazione disponga di autorizzazioni sufficienti per la creazione di oggetti del sistema operativo denominati.  
  
2.  Verificare che Common Language Runtime disponga di autorizzazioni sufficienti per la creazione di file mappati alla memoria.  
  
3.  Riavviare il computer per cancellare i processi che stanno usando la risorsa necessaria per la connessione all'istanza originale.  
  
4.  Prendere nota delle circostanze in cui si è verificato l'errore e contattare il Servizio Supporto Tecnico Clienti Microsoft.  
  
## <a name="see-also"></a>Vedere anche  
 [Pagina Applicazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)  
 [Debugger Basics](/visualstudio/debugger/debugger-basics) (Nozioni di base sul debugger)  
 [Comunicazioni con Microsoft](/visualstudio/ide/talk-to-us)
