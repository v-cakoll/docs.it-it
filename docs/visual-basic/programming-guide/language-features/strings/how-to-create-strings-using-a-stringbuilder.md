---
title: 'Procedura: creare stringhe usando StringBuilder'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 9295b9d0cdcfdb05dfc75f75f48c16c2354b09b0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344377"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Procedura: creare stringhe usando StringBuilder in Visual Basic

Questo esempio crea una stringa estesa da molte stringhe più piccole usando la classe <xref:System.Text.StringBuilder>. La classe <xref:System.Text.StringBuilder> è più efficiente dell'operatore `&=` per la concatenazione di molte stringhe.

## <a name="example"></a>Esempio

Nell'esempio seguente viene creata un'istanza della classe <xref:System.Text.StringBuilder>, vengono accodate 1.000 stringhe a tale istanza, quindi viene restituita la relativa rappresentazione di stringa:

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a>Vedere anche

- [Uso della classe StringBuilder](../../../../standard/base-types/stringbuilder.md)
- [Operatore &=](../../../language-reference/operators/and-assignment-operator.md)
- [Stringhe](index.md)
- [Creazione di nuove stringhe](../../../../standard/base-types/creating-new.md)
- [Modifica di stringhe](../../../../standard/base-types/manipulating-strings.md)
