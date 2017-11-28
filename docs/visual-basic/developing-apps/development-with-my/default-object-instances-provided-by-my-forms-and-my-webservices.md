---
title: Istanze predefinite degli oggetti fornite da My.Forms e My.WebServices (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 44265c3f6f38a001192a8d92f2fbb6edeaca21cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a>Istanze predefinite degli oggetti fornite da My.Forms e My.WebServices (Visual Basic)
Il [Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) e [My. WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) oggetti forniscono accesso ai moduli, origini dati e servizi Web XML utilizzati dall'applicazione. A tal fine alle raccolte di *le istanze predefinite* di ognuno di questi oggetti.  
  
## <a name="default-instances"></a>Istanze predefinite  
 Un'istanza predefinita è un'istanza della classe che viene fornita dal runtime e non deve essere dichiarata e creata un'istanza utilizzando il `Dim` e `New` istruzioni. Nell'esempio seguente viene illustrato come potrebbe avere dichiarato e creare un'istanza di un'istanza di un <xref:System.Windows.Forms.Form> classe denominata `Form1`, e come si sia in grado di ottenere un'istanza predefinita di questo <xref:System.Windows.Forms.Form> classe tramite `My.Forms`.  
  
 [!code-vb[VbVbcnMy#5](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_1.vb)]  
  
 [!code-vb[VbVbcnMy#6](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_2.vb)]  
  
 Il `My.Forms` oggetto restituisce una raccolta di istanze predefinite per ogni `Form` classe presente nel progetto. Analogamente, `My.WebServices` fornisce un'istanza predefinita della classe proxy per ogni servizio Web che hanno creato un riferimento nell'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Oggetto My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [Oggetto My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)  
 [Dipendenza di My dal tipo di progetto](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
