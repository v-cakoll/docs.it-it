---
title: Istanze predefinite degli oggetti fornite da My.Forms e My.WebServices (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 9285e88e3dc9fd8b3731416b1c40811188d6a33d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563600"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a>Istanze predefinite degli oggetti fornite da My.Forms e My.WebServices (Visual Basic)
Il [My. Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) e [My. WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) oggetti forniscono l'accesso a form, origini dati e servizi Web XML usati dall'applicazione. Ciò avviene grazie alle raccolte di *le istanze predefinite* della ognuno di questi oggetti.  
  
## <a name="default-instances"></a>Istanze predefinite  
 Un'istanza predefinita è un'istanza della classe che viene fornita dal runtime e non deve essere dichiarato e creare un'istanza usando il `Dim` e `New` istruzioni. Nell'esempio seguente viene illustrato come si dispone di dichiarare e creare un'istanza di un'istanza di un <xref:System.Windows.Forms.Form> classe denominata `Form1`, e come sono ora in grado di ottenere un'istanza predefinita di questo <xref:System.Windows.Forms.Form> classe tramite `My.Forms`.  
  
 [!code-vb[VbVbcnMy#5](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_1.vb)]  
  
 [!code-vb[VbVbcnMy#6](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_2.vb)]  
  
 Il `My.Forms` object restituisce una raccolta di istanze predefinite di ogni `Form` classe esistente nel progetto. Analogamente, `My.WebServices` fornisce un'istanza predefinita della classe proxy per tutti i servizi Web che hanno creato un riferimento a nell'applicazione.  
  
## <a name="see-also"></a>Vedere anche
- [Oggetto My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [Oggetto My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)
- [Dipendenza di My dal tipo di progetto](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
