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
ms.openlocfilehash: f8ee46b12e84f99629c3a92057fc3a7bb8a3c2e8
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004945"
---
# <a name="order-by-clause-visual-basic"></a>Clausola Order By (Visual Basic)
Specifica l'ordinamento per il risultato di una query.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a>Parti  
 `orderExp1`  
 Obbligatorio. Uno o più campi dal risultato della query corrente che identificano la modalità di ordinamento dei valori restituiti. I nomi dei campi devono essere separati da virgole (,). È possibile identificare ogni campo come ordinato in ordine crescente o decrescente usando le parole chiave `Ascending` o `Descending`. Se non viene specificata alcuna parola chiave `Ascending` o `Descending`, l'ordinamento predefinito è crescente. Ai campi di ordinamento viene assegnata la precedenza da sinistra a destra.  
  
## <a name="remarks"></a>Note  
 È possibile utilizzare la clausola `Order By` per ordinare i risultati di una query. La clausola `Order By` può ordinare solo un risultato in base alla variabile di intervallo per l'ambito corrente. Ad esempio, la clausola `Select` introduce un nuovo ambito in un'espressione di query con nuove variabili di iterazione per tale ambito. Le variabili di intervallo definite prima di una clausola `Select` in una query non sono disponibili dopo la clausola `Select`. Se pertanto si desidera ordinare i risultati in base a un campo non disponibile nella clausola `Select`, è necessario inserire la clausola `Order By` prima della clausola `Select`. Un esempio di quando è necessario eseguire questa operazione è quando si desidera ordinare la query in base a campi che non vengono restituiti come parte del risultato.  
  
 L'ordine crescente e decrescente per un campo è determinato dall'implementazione dell'interfaccia <xref:System.IComparable> per il tipo di dati del campo. Se il tipo di dati non implementa l'interfaccia <xref:System.IComparable>, l'ordinamento viene ignorato.  
  
## <a name="example"></a>Esempio  
 Nell'espressione di query seguente viene utilizzata una clausola `From` per dichiarare una variabile di intervallo `book` per la raccolta `books`. La clausola `Order By` Ordina il risultato della query in base al prezzo in ordine crescente (impostazione predefinita). I libri con lo stesso prezzo vengono ordinati in base al titolo in ordine crescente. La clausola `Select` seleziona le proprietà `Title` e `Price` come valori restituiti dalla query.  
  
 [!code-vb[VbSimpleQuerySamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#24)]  
  
## <a name="example"></a>Esempio  
 Nell'espressione di query seguente viene utilizzata la clausola `Order By` per ordinare il risultato della query in base al prezzo in ordine decrescente. I libri con lo stesso prezzo vengono ordinati in base al titolo in ordine crescente.  
  
 [!code-vb[VbSimpleQuerySamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#25)]  
  
## <a name="example"></a>Esempio  
 Nell'espressione di query seguente viene utilizzata una clausola `Select` per selezionare titolo, prezzo, data di pubblicazione e autore del libro. Quindi popola i campi `Title`, `Price`, `PublishDate` e `Author` della variabile di intervallo per il nuovo ambito. La clausola `Order By` Ordina la nuova variabile di intervallo in base al nome dell'autore, al titolo del libro e quindi al prezzo. Ogni colonna viene ordinata in base all'ordine predefinito (ascendente).  
  
 [!code-vb[VbSimpleQuerySamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#26)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
