---
title: Clausola Select (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySelect
helpviewer_keywords:
- Select statement [Visual Basic]
- Select clause [Visual Basic]
- queries [Visual Basic], Select
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
ms.openlocfilehash: 367d810c2358963bfe2f092a390443eccdc66941
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945262"
---
# <a name="select-clause-visual-basic"></a>Clausola Select (Visual Basic)
Definisce il risultato di una query.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a>Parti  
 `var1`  
 Facoltativo. Un alias che può essere utilizzato per fare riferimento ai risultati dell'espressione.  
  
 `fieldName1`  
 Obbligatorio. Il nome del campo da restituire nel risultato della query.  
  
## <a name="remarks"></a>Note  
 È possibile usare il `Select` clausola per definire i risultati da restituire da una query. In questo modo è possibile definire i membri di un nuovo tipo anonimo che viene creato da una query, o i membri di un tipo denominato che viene restituito da una query di destinazione. Il `Select` clausola non è necessaria per una query. Se nessun `Select` è specificata alcuna clausola, la query verrà restituito un tipo basato su tutti i membri delle variabili di intervallo identificate per l'ambito corrente. Per altre informazioni, vedere [Tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md). Quando una query viene creato un tipo denominato, verrà restituito un risultato di tipo <xref:System.Collections.Generic.IEnumerable%601> in cui `T` è il tipo creato.  
  
 Il `Select` clausola può fare riferimento alle variabili nell'ambito corrente. Ciò include le variabili di intervallo identificate nella `From` clausola (o `From` clausole). Include anche le nuove variabili create con un alias per il `Aggregate`, `Let`, `Group By`, o `Group Join` clausole o le variabili da una precedente `Select` clausola nell'espressione di query. Il `Select` clausola può anche includere valori statici. Ad esempio, il codice seguente viene illustrata un'espressione di query in cui il `Select` clausola definisce il risultato della query come un nuovo tipo anonimo con quattro membri: `ProductName`, `Price`, `Discount`, e `DiscountedPrice`. Il `ProductName` e `Price` i valori del membro provengono dalla variabile di intervallo prodotto definito nel `From` clausola. Il `DiscountedPrice` valore del membro viene calcolato nel `Let` clausola. Il `Discount` membro è un valore statico.  
  
 [!code-vb[VbSimpleQuerySamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#27)]  
  
 Il `Select` clausola introduce un nuovo set di variabili di intervallo per le clausole di query successivi, e le variabili di intervallo precedente non sono più nell'ambito. L'ultimo `Select` clausola in un'espressione di query determina il valore restituito della query. La query seguente restituisce ad esempio, la società nome e l'ID ordine per ogni ordine del cliente per cui il totale superiore a 500. Il primo `Select` clausola identifica le variabili di intervallo per il `Where` clausola e il secondo `Select` clausola. Il secondo `Select` clausola identifica i valori restituiti dalla query come un nuovo tipo anonimo.  
  
 [!code-vb[VbSimpleQuerySamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#28)]  
  
 Se il `Select` clausola identifica un singolo elemento da restituire, l'espressione di query restituisce una raccolta del tipo di quell'unico elemento. Se il `Select` clausola identifica più elementi da restituire, l'espressione di query restituisce una raccolta di un nuovo tipo anonimo, basato sugli elementi selezionati. Ad esempio, le due query seguenti restituiscono raccolte di due tipi diversi in base il `Select` clausola. La prima query restituisce una raccolta di nomi di società come stringhe. La seconda query restituisce una raccolta di `Customer` oggetti popolati con i nomi di società e le informazioni sull'indirizzo.  
  
 [!code-vb[VbSimpleQuerySamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#29)]  
  
## <a name="example"></a>Esempio  
 La query seguente espressione Usa un `From` clausola per dichiarare una variabile di intervallo `cust` per il `customers` raccolta. Il `Select` clausola consente di selezionare il nome del cliente e il valore ID e popola la `CompanyName` e `CustomerID` colonne della nuova variabile di intervallo. Il `For Each` istruzione scorre in ciclo ogni oggetto restituito e consente di visualizzare il `CompanyName` e `CustomerID` colonne per ogni record.  
  
 [!code-vb[VbSimpleQuerySamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#30)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
- [Clausola Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
