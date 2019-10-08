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
ms.openlocfilehash: 88166a040823cfefe623f672e556c364d652a7fc
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004723"
---
# <a name="let-clause-visual-basic"></a>Clausola Let (Visual Basic)
Calcola un valore e lo assegna a una nuova variabile all'interno della query.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a>Parti  
  
|Nome|Definizione|  
|---|---|  
|`variable`|Obbligatorio. Alias che può essere utilizzato per fare riferimento ai risultati dell'espressione fornita.|  
|`expression`|Obbligatorio. Espressione che verrà valutata e assegnata alla variabile specificata.|  
  
## <a name="remarks"></a>Note  
 La clausola `Let` consente di calcolare i valori per ogni risultato della query e di farvi riferimento tramite un alias. L'alias può essere utilizzato in altre clausole, ad esempio la clausola `Where`. La clausola `Let` consente di creare un'istruzione di query più semplice da leggere, in quanto è possibile specificare un alias per una clausola Expression inclusa nella query e sostituire l'alias ogni volta che viene utilizzata la clausola Expression.  
  
 È possibile includere un numero qualsiasi di assegnazioni `variable` e `expression` nella clausola `Let`. Separare ogni assegnazione con una virgola (,).  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene usata la clausola `Let` per calcolare uno sconto del 10% sui prodotti.  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
