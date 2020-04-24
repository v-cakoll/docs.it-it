---
title: Istanze predefinite degli oggetti fornite da My.Forms e My.WebServices
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: d06df4bd023892429b2aaefdd624398a6546d06d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330210"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a>Istanze predefinite degli oggetti fornite da My.Forms e My.WebServices (Visual Basic)

Gli oggetti [My. Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) e [My. WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) consentono di accedere ai moduli, alle origini dati e ai servizi Web XML utilizzati dall'applicazione. A tale scopo, vengono fornite raccolte di *istanze predefinite* di ognuno di questi oggetti.  
  
## <a name="default-instances"></a>Istanze predefinite  

 Un'istanza predefinita è un'istanza della classe fornita dal runtime e non è necessario dichiararla e crearne un'istanza usando le `Dim` istruzioni e. `New` Nell'esempio <xref:System.Windows.Forms.Form> seguente viene illustrato come dichiarare e creare un'istanza di una classe denominata `Form1`e come ora è possibile ottenere un'istanza predefinita di questa <xref:System.Windows.Forms.Form> classe tramite. `My.Forms`  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 L' `My.Forms` oggetto restituisce una raccolta di istanze predefinite per ogni `Form` classe esistente nel progetto. Analogamente `My.WebServices` , fornisce un'istanza predefinita della classe proxy per ogni servizio Web a cui è stato creato un riferimento nell'applicazione.  
  
## <a name="see-also"></a>Vedi anche

- [Oggetto My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [Oggetto My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)
- [Dipendenza di My dal tipo di progetto](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
