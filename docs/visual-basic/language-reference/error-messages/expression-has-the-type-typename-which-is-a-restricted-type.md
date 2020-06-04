---
title: L'espressione è di tipo '<typename>' che corrisponde a un tipo limitato e non può essere utilizzato per accedere ai membri ereditati da 'Object' o 'ValueType'
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 0eb30488312cc7519f39a6b819aea15489f2f70a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409520"
---
# <a name="expression-has-the-type-typename-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-object-or-valuetype"></a>L'espressione è di tipo '\<typename>' che corrisponde a un tipo limitato e non può essere utilizzato per accedere ai membri ereditati da 'Object' o 'ValueType'
Un'espressione restituisce un tipo che non può essere boxed dal Common Language Runtime (CLR) ma accede a un membro che richiede la conversione boxing.  
  
 Il termine*boxing* indica il processo di elaborazione necessario per la conversione di un tipo in `Object` o <xref:System.ValueType>. Il Common Language Runtime non può eseguire il box di determinati tipi di struttura, ad esempio, <xref:System.ArgIterator> <xref:System.RuntimeArgumentHandle> e <xref:System.TypedReference> .  
  
 Questa espressione tenta di usare il tipo con restrizioni per chiamare un metodo ereditato da <xref:System.Object> o <xref:System.ValueType> , ad esempio <xref:System.Object.GetHashCode%2A> o <xref:System.Object.ToString%2A> . Per accedere a questo metodo, Visual Basic ha tentato di eseguire una conversione boxing implicita che genera questo errore.  
  
 **ID errore:** BC31393  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Trovare l'espressione che restituisce il tipo citato.  
  
2. Individuare la parte dell'istruzione che tenta di chiamare il metodo ereditato da <xref:System.Object> o <xref:System.ValueType> .  
  
3. Riscrivere l'istruzione per evitare la chiamata al metodo.  
  
## <a name="see-also"></a>Vedere anche

- [Conversioni implicite ed esplicite](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
