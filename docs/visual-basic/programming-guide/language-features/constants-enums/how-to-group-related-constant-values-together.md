---
title: 'Procedura: raggruppare i valori delle costanti correlate'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: d2393af8b0c2b0c2e528f9908a78fbc7f182c8cf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414440"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a>Procedura: raggruppare i valori delle costanti correlate (Visual Basic)
Un'enumerazione rappresenta il modo migliore per raggruppare le costanti correlate. Si crea un'enumerazione con l' `Enum` istruzione nella sezione delle dichiarazioni di una classe o di un modulo. Per altre informazioni, vedere [procedura: dichiarare un'enumerazione](how-to-declare-enumerations.md).  
  
### <a name="to-group-related-constant-values"></a>Per raggruppare i valori delle costanti correlate  
  
1. Scrivere una dichiarazione che includa un livello di accesso al codice, la `Enum` parola chiave e un nome valido. In questo esempio viene creata l' `Private` enumerazione `temperatureValues` .  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. Definire le costanti nell'enumerazione. Questo esempio crea l' `Public` enumerazione `temperatureValues` e ne assegna i valori.  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Qualifica di nomi ed enumerazioni](enumerations-and-name-qualification.md)
- [Procedura: fare riferimento a un membro di enumerazione](how-to-refer-to-an-enumeration-member.md)
- [Quando utilizzare un'enumerazione](when-to-use-an-enumeration.md)
- [Cenni preliminari sulle costanti](constants-overview.md)
- [Tipi di dati costanti e letterali](constant-and-literal-data-types.md)
- [Costanti ed enumerazioni](../../../language-reference/constants-and-enumerations.md)
