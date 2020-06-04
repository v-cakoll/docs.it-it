---
title: Esecuzione di attività mediante My.Application, My.Computer e My.User
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: 55961d6857b690fc2726f541df8a5497a3207928
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411694"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a>Esecuzione di attività mediante My.Application, My.Computer e My.User (Visual Basic)

I tre `My` oggetti centrali che consentono di accedere alle informazioni e alle funzionalità comunemente utilizzate sono `My.Application` ( <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> ), `My.Computer` ( <xref:Microsoft.VisualBasic.Devices.Computer> ) e `My.User` () <xref:Microsoft.VisualBasic.ApplicationServices.User> . Questi oggetti possono essere usati per accedere alle informazioni relative all'applicazione corrente, al computer in cui è installata l'applicazione o all'utente corrente dell'applicazione.  
  
## <a name="myapplication-mycomputer-and-myuser"></a>My. Application, My. computer e My. User  

 Gli esempi seguenti illustrano come è possibile recuperare le informazioni usando `My` .  
  
 [!code-vb[VbVbcnMy#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbcnMy#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#2)]  
  
 Oltre a recuperare le informazioni, i membri esposti tramite questi tre oggetti consentono inoltre di eseguire metodi correlati a tale oggetto. Ad esempio, è possibile accedere a diversi metodi per modificare i file o aggiornare il registro di sistema tramite `My.Computer` .  
  
 L'I/O dei file è significativamente più semplice e veloce con `My` , che include un'ampia gamma di metodi e proprietà per la modifica di file, directory e unità. L' <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> oggetto consente di leggere da file strutturati di grandi dimensioni con campi delimitati o a larghezza fissa. In questo esempio viene aperto `TextFieldParser` `reader` e utilizzato per leggere da `C:\TestFolder1\test1.txt` .  
  
 [!code-vb[VbVbalrTextFieldParser#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTextFieldParser/VB/Class1.vb#23)]  
  
 `My.Application`consente di modificare le impostazioni cultura per l'applicazione. Nell'esempio seguente viene illustrato come è possibile chiamare questo metodo.  
  
 [!code-vb[VbVbcnMy#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Dipendenza di My dal tipo di progetto](how-my-depends-on-project-type.md)
