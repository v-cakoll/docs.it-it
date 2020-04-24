---
title: 'Procedura: creare stringhe usando un oggetto StringBuilderHow to: create strings using a StringBuilder'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: c41db584df83782dab99b90043045aa2cabcb6ff
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645332"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>Procedura: creare stringhe utilizzando un oggetto StringBuilder in Visual BasicHow to: create strings using a StringBuilder in Visual Basic

In questo esempio viene costruita una <xref:System.Text.StringBuilder> stringa lunga da molte stringhe più piccole utilizzando la classe . La <xref:System.Text.StringBuilder> classe è più `&=` efficiente dell'operatore per la concatenazione di molte stringhe.

## <a name="example"></a>Esempio

Nell'esempio seguente viene <xref:System.Text.StringBuilder> creata un'istanza della classe, vengono aggiunte 1.000 stringhe a tale istanza e quindi viene restituita la relativa rappresentazione di stringa:

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a>Vedere anche

- [Uso della classe StringBuilder](../../../../standard/base-types/stringbuilder.md)
- [&- Operatore](../../../language-reference/operators/and-assignment-operator.md)
- [Stringhe](index.md)
- [Creazione di nuove stringhe](../../../../standard/base-types/creating-new.md)
- [Modifica di stringhe](../../../../standard/base-types/best-practices-strings.md)
