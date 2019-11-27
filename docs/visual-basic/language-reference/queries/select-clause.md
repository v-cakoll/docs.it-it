---
title: Clausola Select
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySelect
helpviewer_keywords:
- Select statement [Visual Basic]
- Select clause [Visual Basic]
- queries [Visual Basic], Select
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
ms.openlocfilehash: 5ebb813229d5d517b369036c69b2d23c8ee1c9f5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350414"
---
# <a name="select-clause-visual-basic"></a>Clausola Select (Visual Basic)
Definisce il risultato di una query.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a>Parti  
 `var1`  
 Facoltativa. Alias che può essere utilizzato per fare riferimento ai risultati dell'espressione di colonna.  
  
 `fieldName1`  
 Obbligatoria. Nome del campo da restituire nel risultato della query.  
  
## <a name="remarks"></a>Note  
 È possibile utilizzare la clausola `Select` per definire i risultati che devono essere restituiti da una query. Ciò consente di definire i membri di un nuovo tipo anonimo creato da una query o di destinare i membri di un tipo denominato restituito da una query. La clausola `Select` non è obbligatoria per una query. Se non viene specificata alcuna clausola `Select`, la query restituirà un tipo basato su tutti i membri delle variabili di intervallo identificate per l'ambito corrente. Per altre informazioni, vedere [Tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md). Quando una query crea un tipo denominato, viene restituito un risultato di tipo <xref:System.Collections.Generic.IEnumerable%601> dove `T` è il tipo creato.  
  
 La clausola `Select` può fare riferimento a qualsiasi variabile nell'ambito corrente. Sono incluse le variabili di intervallo identificate nella clausola `From` o `From` clausole. Include anche tutte le nuove variabili create con un alias dalle clausole `Aggregate`, `Let`, `Group By`o `Group Join` o dalle variabili di una clausola di `Select` precedente nell'espressione di query. La clausola `Select` può includere anche valori statici. Nell'esempio di codice seguente, ad esempio, viene illustrata un'espressione di query in cui la clausola `Select` definisce il risultato della query come nuovo tipo anonimo con quattro membri: `ProductName`, `Price`, `Discount`e `DiscountedPrice`. I valori dei membri `ProductName` e `Price` sono ricavati dalla variabile di intervallo di prodotti definita nella clausola `From`. Il valore del membro `DiscountedPrice` viene calcolato nella clausola `Let`. Il `Discount` membro è un valore statico.  
  
 [!code-vb[VbSimpleQuerySamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#27)]  
  
 La clausola `Select` introduce un nuovo set di variabili di intervallo per le clausole di query successive e le variabili di intervallo precedenti non sono più nell'ambito. L'ultima clausola `Select` in un'espressione di query determina il valore restituito dalla query. Ad esempio, la query seguente restituisce il nome e l'ID dell'azienda per ogni ordine cliente per il quale il totale supera 500. La prima clausola `Select` identifica le variabili di intervallo per la clausola `Where` e la seconda clausola `Select`. La seconda clausola `Select` identifica i valori restituiti dalla query come un nuovo tipo anonimo.  
  
 [!code-vb[VbSimpleQuerySamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#28)]  
  
 Se la clausola `Select` identifica un singolo elemento da restituire, l'espressione di query restituisce una raccolta del tipo di quel singolo elemento. Se la clausola `Select` identifica più elementi da restituire, l'espressione di query restituisce una raccolta di un nuovo tipo anonimo, in base agli elementi selezionati. Ad esempio, le due query seguenti restituiscono raccolte di due tipi diversi in base alla clausola `Select`. La prima query restituisce una raccolta di nomi di società come stringhe. La seconda query restituisce una raccolta di oggetti `Customer` popolati con i nomi e le informazioni sull'indirizzo della società.  
  
 [!code-vb[VbSimpleQuerySamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#29)]  
  
## <a name="example"></a>Esempio  
 Nell'espressione di query seguente viene utilizzata una clausola `From` per dichiarare una variabile di intervallo `cust` per la raccolta di `customers`. La clausola `Select` seleziona il nome e il valore ID del cliente e popola le colonne `CompanyName` e `CustomerID` della nuova variabile di intervallo. L'istruzione `For Each` esegue il ciclo di ogni oggetto restituito e visualizza le colonne `CompanyName` e `CustomerID` per ogni record.  
  
 [!code-vb[VbSimpleQuerySamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#30)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
- [Clausola Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
