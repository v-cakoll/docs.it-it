---
title: Come scrivere un costruttore di copia- C# Guida alla programmazione
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: 4ac7ccb55775019eb86d5345797d2fd74d3b9527
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73970395"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a>Come scrivere un costruttore di copia (C# guida per programmatori)
C# non include un costruttore di copia per gli oggetti. È tuttavia possibile scriverne uno manualmente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, nella `Person`[classe](../../language-reference/keywords/class.md) viene definito un costruttore di copia che accetta come argomento un'istanza di `Person`. I valori delle proprietà dell'argomento vengono assegnati alle proprietà della nuova istanza di `Person`. Il codice contiene un costruttore di copia alternativo che invia le proprietà `Name` e `Age` dell'istanza che si vuole copiare nel costruttore di istanza della classe.  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ICloneable>
- [Guida per programmatori C#](../index.md)
- [Classi e struct](./index.md)
- [Costruttori](./constructors.md)
- [Finalizzatori](./destructors.md)
