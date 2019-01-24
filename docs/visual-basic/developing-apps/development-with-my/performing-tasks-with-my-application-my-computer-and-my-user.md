---
title: Esecuzione di attività mediante My.Application, My.Computer e My.User (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: 5340c137842591bb1f4408392e02329fb2a491ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651630"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a>Esecuzione di attività mediante My.Application, My.Computer e My.User (Visual Basic)
I tre principali `My` sono oggetti che forniscono funzionalità di accesso a informazioni e comunemente utilizzata `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), e `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>). È possibile usare questi oggetti per accedere alle informazioni correlate per l'applicazione corrente, che l'applicazione è installata nel computer o l'utente corrente dell'applicazione, rispettivamente.  
  
## <a name="myapplication-mycomputer-and-myuser"></a>My. Application, My. computer e My. User  
 Gli esempi seguenti illustrano come le informazioni possono essere recuperati tramite `My`.  
  
 [!code-vb[VbVbcnMy#1](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_1.vb)]  
  
 [!code-vb[VbVbcnMy#2](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_2.vb)]  
  
 Oltre il recupero di informazioni, i membri esposti attraverso i tre oggetti consentono anche di eseguire i metodi correlati a tale oggetto. Ad esempio, è possibile accedere un'ampia gamma di metodi per modificare i file o aggiornare il Registro di sistema tramite `My.Computer`.  
  
 I/o file è notevolmente più semplice e rapido con `My`, che include un'ampia gamma di metodi e proprietà per la modifica dei file, directory e le unità. Il <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> oggetto consente di leggere da file strutturati di grandi dimensioni che sono delimitati o campi a larghezza fissa. In questo esempio si apre la `TextFieldParser` `reader` e lo usa per leggere da `C:\TestFolder1\test1.txt`.  
  
 [!code-vb[VbVbalrTextFieldParser#23](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_3.vb)]  
  
 `My.Application` Consente di modificare le impostazioni cultura per l'applicazione. Nell'esempio seguente viene illustrato come può chiamare questo metodo.  
  
 [!code-vb[VbVbcnMy#3](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_4.vb)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Dipendenza di My dal tipo di progetto](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
