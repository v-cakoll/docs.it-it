---
title: Espressione è di tipo &#39; &lt;nomeTipo&gt; &#39; che è un tipo con restrizioni e non può essere usato per accedere ai membri ereditati da &#39;oggetto&#39; o &#39;ValueType&#39;
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: d44b9a29f0848508d8cd814e857d9b01819ce7ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535957"
---
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a>Espressione è di tipo &#39; &lt;nomeTipo&gt; &#39; che è un tipo con restrizioni e non può essere usato per accedere ai membri ereditati da &#39;oggetto&#39; o &#39;ValueType&#39;
Un'espressione restituisce un tipo che non può essere boxed da common language runtime (CLR), ma accede a un membro che richiede il boxing.  
  
 Il termine*boxing* indica il processo di elaborazione necessario per la conversione di un tipo in `Object` o <xref:System.ValueType>. Common language runtime non supporta il boxing determinati tipi di struttura, ad esempio <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, e <xref:System.TypedReference>.  
  
 Questa espressione tenta di usare il tipo con restrizioni per chiamare un metodo ereditato da <xref:System.Object> oppure <xref:System.ValueType>, ad esempio <xref:System.Object.GetHashCode%2A> o <xref:System.Object.ToString%2A>. Per accedere a questo metodo, Visual Basic ha tentato di una conversione boxing implicita che genera questo errore.  
  
 **ID errore:** BC31393  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Trovare l'espressione che restituisce il tipo citato.  
  
2.  Individuare la parte dell'istruzione che prova a chiamare il metodo ereditato da <xref:System.Object> o <xref:System.ValueType>.  
  
3.  Riscrivere le istruzioni per evitare la chiamata al metodo.  
  
## <a name="see-also"></a>Vedere anche
- [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
