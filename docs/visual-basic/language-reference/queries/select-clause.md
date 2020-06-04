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
ms.openlocfilehash: a909b1d79b10f82ece03bab788ae889c64b27124
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359694"
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
 Obbligatorio. Nome del campo da restituire nel risultato della query.  
  
## <a name="remarks"></a>Commenti  
 È possibile utilizzare la `Select` clausola per definire i risultati che devono essere restituiti da una query. Ciò consente di definire i membri di un nuovo tipo anonimo creato da una query o di destinare i membri di un tipo denominato restituito da una query. La `Select` clausola non è obbligatoria per una query. Se non `Select` viene specificata alcuna clausola, la query restituirà un tipo basato su tutti i membri delle variabili di intervallo identificate per l'ambito corrente. Per ulteriori informazioni, vedere [tipi anonimi](../../programming-guide/language-features/objects-and-classes/anonymous-types.md). Quando una query crea un tipo denominato, restituirà un risultato di tipo <xref:System.Collections.Generic.IEnumerable%601> dove `T` è il tipo creato.  
  
 La `Select` clausola può fare riferimento a qualsiasi variabile nell'ambito corrente. Sono incluse le variabili di intervallo identificate nella `From` clausola o nelle `From` clausole. Include anche tutte le nuove variabili create con un alias dalle `Aggregate` `Let` `Group By` clausole,, o o `Group Join` dalle variabili di una `Select` clausola precedente nell'espressione di query. La `Select` clausola può includere anche valori statici. Nell'esempio di codice seguente, ad esempio, viene illustrata un'espressione di query in cui la `Select` clausola definisce il risultato della query come nuovo tipo anonimo con quattro membri: `ProductName` , `Price` , `Discount` e `DiscountedPrice` . I `ProductName` `Price` valori dei membri e vengono ricavati dalla variabile di intervallo di prodotti definita nella `From` clausola. Il `DiscountedPrice` valore del membro viene calcolato nella `Let` clausola. Il `Discount` membro è un valore statico.  
  
 [!code-vb[VbSimpleQuerySamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#27)]  
  
 La `Select` clausola introduce un nuovo set di variabili di intervallo per le clausole di query successive e le variabili di intervallo precedenti non sono più nell'ambito. L'ultima `Select` clausola in un'espressione di query determina il valore restituito dalla query. Ad esempio, la query seguente restituisce il nome e l'ID dell'azienda per ogni ordine cliente per il quale il totale supera 500. La prima `Select` clausola identifica le variabili di intervallo per la `Where` clausola e la seconda `Select` clausola. La seconda `Select` clausola identifica i valori restituiti dalla query come un nuovo tipo anonimo.  
  
 [!code-vb[VbSimpleQuerySamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#28)]  
  
 Se la `Select` clausola identifica un singolo elemento da restituire, l'espressione di query restituisce una raccolta del tipo di quel singolo elemento. Se la `Select` clausola identifica più elementi da restituire, l'espressione di query restituisce una raccolta di un nuovo tipo anonimo, in base agli elementi selezionati. Ad esempio, le due query seguenti restituiscono raccolte di due tipi diversi in base alla `Select` clausola. La prima query restituisce una raccolta di nomi di società come stringhe. La seconda query restituisce una raccolta di `Customer` oggetti popolati con i nomi e le informazioni sull'indirizzo della società.  
  
 [!code-vb[VbSimpleQuerySamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#29)]  
  
## <a name="example"></a>Esempio  
 Nell'espressione di query seguente viene utilizzata una `From` clausola per dichiarare una variabile di intervallo `cust` per la `customers` raccolta. La `Select` clausola seleziona il nome e il valore ID del cliente e popola `CompanyName` le `CustomerID` colonne e della nuova variabile di intervallo. L' `For Each` istruzione esegue il ciclo di ogni oggetto restituito e visualizza le `CompanyName` `CustomerID` colonne e per ogni record.  
  
 [!code-vb[VbSimpleQuerySamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#30)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](index.md)
- [Clausola from](from-clause.md)
- [Clausola WHERE](where-clause.md)
- [Clausola Order By](order-by-clause.md)
- [Tipi anonimi](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
