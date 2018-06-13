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
ms.openlocfilehash: 55c1e79b9e8e26483c1b7374a755bf977129169b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604406"
---
# <a name="select-clause-visual-basic"></a>Clausola Select (Visual Basic)
Definisce il risultato di una query.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a>Parti  
 `var1`  
 Facoltativo. Un alias che può essere usato per fare riferimento ai risultati dell'espressione di colonna.  
  
 `fieldName1`  
 Obbligatorio. Il nome del campo da restituire nel risultato della query.  
  
## <a name="remarks"></a>Note  
 È possibile utilizzare il `Select` clausola per definire i risultati da restituire da una query. Ciò consente di definire i membri di un nuovo tipo anonimo che viene creato da una query o per i membri di un tipo denominato restituito da una query di destinazione. Il `Select` clausola non è obbligatoria per una query. Se nessun `Select` è specificata alcuna clausola, la query restituirà un tipo di base per tutti i membri delle variabili di intervallo identificate per l'ambito corrente. Per altre informazioni, vedere [Tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md). Quando una query viene creato un tipo denominato, verrà restituito un risultato di tipo <xref:System.Collections.Generic.IEnumerable%601> dove `T` è il tipo creato.  
  
 Il `Select` clausola può fare riferimento a tutte le variabili nell'ambito corrente. Ciò include le variabili di intervallo identificate nella `From` clausola (o `From` clausole). Include inoltre le nuove variabili create con un alias per il `Aggregate`, `Let`, `Group By`, o `Group Join` clausole o le variabili da una precedente `Select` clausola nell'espressione di query. Il `Select` clausola può inoltre includere valori statici. Ad esempio, l'esempio di codice seguente viene illustrata un'espressione di query in cui il `Select` clausola definisce il risultato della query come un nuovo tipo anonimo con quattro membri: `ProductName`, `Price`, `Discount`, e `DiscountedPrice`. Il `ProductName` e `Price` valori del membro provengono dalla variabile di intervallo prodotto definito nel `From` clausola. Il `DiscountedPrice` membro valore viene calcolato nel `Let` clausola. Il `Discount` membro è un valore statico.  
  
 [!code-vb[VbSimpleQuerySamples#27](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_1.vb)]  
  
 Il `Select` clausola introduce un nuovo set di variabili di intervallo per successive clausole di query e variabili di intervallo precedenti non sono più in ambito. L'ultimo `Select` clausola in un'espressione di query determina il valore restituito della query. La query seguente restituisce ad esempio, la società nome e l'ID ordine per ogni ordine del cliente per cui il totale supera 500. Il primo `Select` clausola identifica le variabili di intervallo per il `Where` clausola e il secondo `Select` clausola. Il secondo `Select` clausola identifica i valori restituiti dalla query come un nuovo tipo anonimo.  
  
 [!code-vb[VbSimpleQuerySamples#28](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_2.vb)]  
  
 Se il `Select` clausola identifica un singolo elemento da restituire, l'espressione di query restituisce una raccolta del tipo di tale elemento unico. Se il `Select` clausola identifica più elementi da restituire, l'espressione di query restituisce una raccolta di un nuovo tipo anonimo, in base agli elementi selezionati. Ad esempio, le due query seguenti restituiscono raccolte di due tipi diversi in base il `Select` clausola. La prima query restituisce una raccolta di nomi di società come stringhe. La seconda query restituisce una raccolta di `Customer` oggetti popolati con i nomi di società e le informazioni sull'indirizzo.  
  
 [!code-vb[VbSimpleQuerySamples#29](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_3.vb)]  
  
## <a name="example"></a>Esempio  
 La query seguente espressione utilizza un `From` clausola per dichiarare una variabile di intervallo `cust` per il `customers` insieme. Il `Select` clausola consente di selezionare il nome del cliente e il valore ID e popola la `CompanyName` e `CustomerID` le colonne della nuova variabile di intervallo. Il `For Each` istruzione esegue un ciclo per ogni oggetto restituito e visualizza il `CompanyName` e `CustomerID` colonne per ogni record.  
  
 [!code-vb[VbSimpleQuerySamples#30](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_4.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Query](../../../visual-basic/language-reference/queries/queries.md)  
 [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Clausola Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
