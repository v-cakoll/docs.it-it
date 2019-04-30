---
title: Istanze predefinite degli oggetti fornite da My.Forms e My.WebServices (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: ca31e1c40c77bf7f42d246019d81f4ffaed646e8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62014453"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a>Istanze predefinite degli oggetti fornite da My.Forms e My.WebServices (Visual Basic)
Il [My. Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) e [My. WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) oggetti forniscono l'accesso a form, origini dati e servizi Web XML usati dall'applicazione. Ciò avviene grazie alle raccolte di *le istanze predefinite* della ognuno di questi oggetti.  
  
## <a name="default-instances"></a>Istanze predefinite  
 Un'istanza predefinita è un'istanza della classe che viene fornita dal runtime e non deve essere dichiarato e creare un'istanza usando il `Dim` e `New` istruzioni. Nell'esempio seguente viene illustrato come si dispone di dichiarare e creare un'istanza di un'istanza di un <xref:System.Windows.Forms.Form> classe denominata `Form1`, e come sono ora in grado di ottenere un'istanza predefinita di questo <xref:System.Windows.Forms.Form> classe tramite `My.Forms`.  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 Il `My.Forms` object restituisce una raccolta di istanze predefinite di ogni `Form` classe esistente nel progetto. Analogamente, `My.WebServices` fornisce un'istanza predefinita della classe proxy per tutti i servizi Web che hanno creato un riferimento a nell'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Oggetto My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [Oggetto My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)
- [Dipendenza di My dal tipo di progetto](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
