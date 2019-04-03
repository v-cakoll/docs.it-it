---
title: Clausola Order By (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
ms.openlocfilehash: 1c84a4cdb4a149154d459ca4d9c290ed360d1772
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835011"
---
# <a name="order-by-clause-visual-basic"></a>Clausola Order By (Visual Basic)
Specifica l'ordinamento dei risultati della query.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a>Parti  
 `orderExp1`  
 Obbligatorio. Uno o più campi dai risultati della query corrente che identificano come ordinare i valori restituiti. I nomi dei campi devono essere separati da virgole (,). È possibile identificare ogni campo, come ordinato in ordine crescente o decrescente usando la `Ascending` o `Descending` parole chiave. Se nessun `Ascending` o `Descending` (parola chiave) viene specificato, l'ordinamento predefinito è crescente. I campi di ordinamento ha la precedenza da sinistra a destra.  
  
## <a name="remarks"></a>Note  
 È possibile usare il `Order By` clausola per ordinare i risultati di una query. Il `Order By` clausola solo possibile ordinare un risultato basato sulla variabile di intervallo per l'ambito corrente. Ad esempio, il `Select` clausola introduce un nuovo ambito in un'espressione di query con nuove variabili di iterazione per tale ambito. Le variabili definite prima di intervallo un `Select` clausola in una query non sono disponibili dopo il `Select` clausola. Pertanto, se si desidera ordinare i risultati tramite un campo che non è disponibile nel `Select` clausola, è necessario inserire il `Order By` clausola prima il `Select` clausola. Un esempio di quando è necessario eseguire questa operazione è quando si desidera ordinare query in base a campi che non vengono restituiti come parte del risultato.  
  
 Ordine crescente o decrescente per un campo è determinato dall'implementazione del <xref:System.IComparable> interfaccia per il tipo di dati del campo. Se il tipo di dati non implementa il <xref:System.IComparable> interfaccia, l'ordinamento viene ignorato.  
  
## <a name="example"></a>Esempio  
 La query seguente espressione Usa un `From` clausola per dichiarare una variabile di intervallo `book` per il `books` raccolta. Il `Order By` clausola consente di ordinare i risultati della query in base al prezzo in modo crescente (impostazione predefinita). Documentazione con lo stesso prezzo sono ordinati per titolo in ordine crescente. Il `Select` clausola consente di selezionare il `Title` e `Price` proprietà come valori restituiti dalla query.  
  
 [!code-vb[VbSimpleQuerySamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#24)]  
  
## <a name="example"></a>Esempio  
 La query seguente Usa espressione di `Order By` clausola per ordinare i risultati della query in base al prezzo in ordine decrescente. Documentazione con lo stesso prezzo sono ordinati per titolo in ordine crescente.  
  
 [!code-vb[VbSimpleQuerySamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#25)]  
  
## <a name="example"></a>Esempio  
 La query seguente espressione utilizza un `Select` clausola per selezionare il titolo del libro, prezzo, data di pubblicazione e la creazione. Viene quindi popolato il `Title`, `Price`, `PublishDate`, e `Author` campi della variabile di intervallo per il nuovo ambito. Il `Order By` clausola ordina la nuova variabile di intervallo per il nome dell'autore, titolo del libro e prezzo. Ogni colonna è ordinata l'ordine predefinito (crescente).  
  
 [!code-vb[VbSimpleQuerySamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#26)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
