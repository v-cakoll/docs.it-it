---
title: Errore imprevisto. Impossibile acquisire una risorsa del sistema operativo necessaria per l'avvio di istanze singole
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_CantGetMemoryMappedFile
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
ms.openlocfilehash: 9aa7ba0babe0a89942e320a76e07c05162b31700
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61751618"
---
# <a name="an-unexpected-error-has-occurred-because-an-operating-system-resource-required-for-single-instance-startup-cannot-be-acquired"></a>Errore imprevisto. Impossibile acquisire una risorsa del sistema operativo necessaria per l'avvio di istanze singole
L'applicazione non è riuscita ad acquisire una risorsa del sistema operativo necessaria. Alcune possibili cause di questo problema sono:  
  
- L'applicazione non dispone di autorizzazioni per la creazione di oggetti del sistema operativo denominati.  
  
- Common Language Runtime non dispone di autorizzazioni per la creazione di file mappati alla memoria.  
  
- L'applicazione deve accedere a un oggetto del sistema operativo, ma un altro processo lo sta usando.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Verificare che l'applicazione disponga di autorizzazioni sufficienti per la creazione di oggetti del sistema operativo denominati.  
  
2. Verificare che Common Language Runtime disponga di autorizzazioni sufficienti per la creazione di file mappati alla memoria.  
  
3. Riavviare il computer per cancellare i processi che stanno usando la risorsa necessaria per la connessione all'istanza originale.  
  
4. Prendere nota delle circostanze in cui si è verificato l'errore e contattare il Servizio Supporto Tecnico Clienti Microsoft.  
  
## <a name="see-also"></a>Vedere anche

- [Pagina Applicazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [Debugger Basics](/visualstudio/debugger/debugger-basics) (Nozioni di base sul debugger)
- [Talk to Us](/visualstudio/ide/talk-to-us) (Comunicazioni con Microsoft)
