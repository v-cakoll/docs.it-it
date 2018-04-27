---
title: Espressione è di tipo &#39; &lt;typename&gt; &#39; che è un tipo con restrizioni e non può essere utilizzato per accedere ai membri ereditati da &#39;oggetto&#39; o &#39;ValueType&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ab4e48c93a6a3c645bf9b5cc6c536d418022ae86
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a>Espressione è di tipo &#39; &lt;typename&gt; &#39; che è un tipo con restrizioni e non può essere utilizzato per accedere ai membri ereditati da &#39;oggetto&#39; o &#39;ValueType&#39;
Un'espressione restituisce un tipo che non può essere sottoposto a boxing tramite common language runtime (CLR), ma accede a un membro che richiede una conversione boxing.  
  
 Il termine*boxing* indica il processo di elaborazione necessario per la conversione di un tipo in `Object` o <xref:System.ValueType>. Common language runtime non supporta il boxing determinati tipi di struttura, ad esempio <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, e <xref:System.TypedReference>.  
  
 Questa espressione tenta di utilizzare il tipo con restrizioni per chiamare un metodo ereditato da <xref:System.Object> o <xref:System.ValueType>, ad esempio <xref:System.Object.GetHashCode%2A> o <xref:System.Object.ToString%2A>. Per accedere a questo metodo, Visual Basic è tentata una conversione boxing implicita che genera questo errore.  
  
 **ID errore:** BC31393  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Trovare l'espressione che restituisce il tipo citato.  
  
2.  Individuare la parte dell'istruzione che tenta di chiamare il metodo ereditato da <xref:System.Object> o <xref:System.ValueType>.  
  
3.  Riscrivere le istruzioni per evitare la chiamata al metodo.  
  
## <a name="see-also"></a>Vedere anche  
 [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
