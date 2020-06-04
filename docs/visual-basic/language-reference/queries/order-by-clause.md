---
title: Clausola Order By
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
ms.openlocfilehash: 63f454064e88bc18f252940f3abd8e59b8900e5b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359748"
---
# <a name="order-by-clause-visual-basic"></a>Clausola Order By (Visual Basic)
Specifica l'ordinamento per il risultato di una query.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a>Parti  
 `orderExp1`  
 Obbligatorio. Uno o più campi dal risultato della query corrente che identificano la modalità di ordinamento dei valori restituiti. I nomi dei campi devono essere separati da virgole (,). È possibile identificare ogni campo come ordinato in ordine crescente o decrescente usando le `Ascending` `Descending` parole chiave o. Se non `Ascending` `Descending` viene specificata alcuna parola chiave o, l'ordinamento predefinito è crescente. Ai campi di ordinamento viene assegnata la precedenza da sinistra a destra.  
  
## <a name="remarks"></a>Commenti  
 È possibile utilizzare la `Order By` clausola per ordinare i risultati di una query. La `Order By` clausola può ordinare solo un risultato in base alla variabile di intervallo per l'ambito corrente. Ad esempio, la `Select` clausola introduce un nuovo ambito in un'espressione di query con nuove variabili di iterazione per tale ambito. Le variabili di intervallo definite prima `Select` di una clausola in una query non sono disponibili dopo la `Select` clausola. Se pertanto si desidera ordinare i risultati in base a un campo non disponibile nella `Select` clausola, è necessario inserire la `Order By` clausola prima della `Select` clausola. Un esempio di quando è necessario eseguire questa operazione è quando si desidera ordinare la query in base a campi che non vengono restituiti come parte del risultato.  
  
 L'ordine crescente e decrescente per un campo è determinato dall'implementazione dell' <xref:System.IComparable> interfaccia per il tipo di dati del campo. Se il tipo di dati non implementa l' <xref:System.IComparable> interfaccia, l'ordinamento viene ignorato.  
  
## <a name="example"></a>Esempio  
 Nell'espressione di query seguente viene utilizzata una `From` clausola per dichiarare una variabile di intervallo `book` per la `books` raccolta. La `Order By` clausola Ordina il risultato della query in base al prezzo in ordine crescente (impostazione predefinita). I libri con lo stesso prezzo vengono ordinati in base al titolo in ordine crescente. La `Select` clausola seleziona le `Title` `Price` proprietà e come valori restituiti dalla query.  
  
 [!code-vb[VbSimpleQuerySamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#24)]  
  
## <a name="example"></a>Esempio  
 Nell'espressione di query seguente viene utilizzata la `Order By` clausola per ordinare il risultato della query in base al prezzo in ordine decrescente. I libri con lo stesso prezzo vengono ordinati in base al titolo in ordine crescente.  
  
 [!code-vb[VbSimpleQuerySamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#25)]  
  
## <a name="example"></a>Esempio  
 Nell'espressione di query seguente viene utilizzata una `Select` clausola per selezionare titolo, prezzo, data di pubblicazione e autore. Quindi compila i `Title` `Price` campi,, `PublishDate` e `Author` della variabile di intervallo per il nuovo ambito. La `Order By` clausola Ordina la nuova variabile di intervallo in base al nome dell'autore, al titolo del libro e quindi al prezzo. Ogni colonna viene ordinata in base all'ordine predefinito (ascendente).  
  
 [!code-vb[VbSimpleQuerySamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#26)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](index.md)
- [Clausola SELECT](select-clause.md)
- [Clausola from](from-clause.md)
