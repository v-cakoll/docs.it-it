---
title: Clausola Order By (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 21ee21942b966668a67b14aba72b8f9fc5ee903c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="order-by-clause-visual-basic"></a>Clausola Order By (Visual Basic)
Specifica l'ordinamento dei risultati di una query.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a>Parti  
 `orderExp1`  
 Obbligatorio. Uno o più campi dai risultati della query corrente che specificano come ordinare i valori restituiti. I nomi dei campi devono essere separati da virgole (,). È possibile identificare ogni campo, come ordinato in ordine crescente o decrescente utilizzando il `Ascending` o `Descending` parole chiave. Se non `Ascending` o `Descending` (parola chiave) è specificato, l'ordinamento predefinito è crescente. I campi di ordinamento ha la precedenza da sinistra a destra.  
  
## <a name="remarks"></a>Note  
 È possibile utilizzare il `Order By` clausola per ordinare i risultati di una query. Il `Order By` clausola può ordinare solo un risultato in base alla variabile di intervallo per l'ambito corrente. Ad esempio, il `Select` clausola introduce un nuovo ambito in un'espressione di query con nuove variabili di iterazione per tale ambito. Le variabili definite prima di intervallo un `Select` in una query non sono disponibili dopo il `Select` clausola. Pertanto, se si desidera ordinare i risultati in base a un campo che non è disponibile nel `Select` clausola, è necessario inserire il `Order By` clausola prima il `Select` clausola. Un esempio di quando è necessario eseguire questa operazione è quando si desidera ordinare la query per i campi che non vengono restituiti come parte del risultato.  
  
 Ordinamento crescente e decrescente per un campo è determinato dall'implementazione del <xref:System.IComparable> interfaccia per il tipo di dati del campo. Se il tipo di dati non implementa il <xref:System.IComparable> interfaccia, l'ordinamento viene ignorato.  
  
## <a name="example"></a>Esempio  
 La query seguente espressione utilizza un `From` clausola per dichiarare una variabile di intervallo `book` per il `books` insieme. Il `Order By` clausola ordina i risultati della query in base al prezzo in senso crescente (impostazione predefinita). Documentazione con lo stesso prezzo vengono ordinati in base a titolo in ordine crescente. Il `Select` clausola seleziona il `Title` e `Price` proprietà come valori restituiti dalla query.  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## <a name="example"></a>Esempio  
 La query seguente espressione utilizza la `Order By` clausola per ordinare il risultato della query in base al prezzo in ordine decrescente. Documentazione con lo stesso prezzo vengono ordinati in base a titolo in ordine crescente.  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## <a name="example"></a>Esempio  
 La query seguente espressione utilizza un `Select` clausola per selezionare il titolo del libro, prezzo, data di pubblicazione e la creazione. Viene quindi popolato il `Title`, `Price`, `PublishDate`, e `Author` campi della variabile di intervallo per il nuovo ambito. Il `Order By` clausola ordina la nuova variabile di intervallo per il nome dell'autore, titolo del libro e prezzo. Ogni colonna viene ordinata in ordine predefinito (crescente).  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Query](../../../visual-basic/language-reference/queries/queries.md)  
 [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
