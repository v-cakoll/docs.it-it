---
title: Clausola Let (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 6484da5329c8240735b7c35f506637dd01cbeda4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604471"
---
# <a name="let-clause-visual-basic"></a>Clausola Let (Visual Basic)
Calcola un valore e lo assegna a una nuova variabile all'interno della query.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`variable`|Obbligatorio. Un alias che può essere usato per fare riferimento ai risultati dell'espressione fornita.|  
|`expression`|Obbligatorio. Un'espressione che verrà valutata e assegnata alla variabile specificata.|  
  
## <a name="remarks"></a>Note  
 Il `Let` clausola consente di calcolare valori per ogni risultato della query e farvi riferimento utilizzando un alias. L'alias può essere utilizzato in altre clausole, ad esempio il `Where` clausola. Il `Let` clausola consente di creare un'istruzione di query che è facile leggere perché è possibile specificare un alias per una clausola dell'espressione inclusa nella query e sostituire l'alias ogni volta che viene utilizzata la clausola dell'espressione.  
  
 È possibile includere un numero qualsiasi di `variable` e `expression` le assegnazioni di `Let` clausola. Separare ogni assegnazione con una virgola (,).  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice viene illustrato come utilizzare il `Let` clausola per calcolare uno sconto del 10% per i prodotti.  
  
 [!code-vb[VbSimpleQuerySamples#16](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/let-clause_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Query](../../../visual-basic/language-reference/queries/queries.md)  
 [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
