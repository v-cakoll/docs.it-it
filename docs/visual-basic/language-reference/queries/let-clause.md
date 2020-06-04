---
title: Clausola Let
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 4bf832651d9753c41ee5a02defec4adc55af1ff1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359761"
---
# <a name="let-clause-visual-basic"></a>Clausola Let (Visual Basic)
Calcola un valore e lo assegna a una nuova variabile all'interno della query.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`variable`|Obbligatorio. Alias che può essere utilizzato per fare riferimento ai risultati dell'espressione fornita.|  
|`expression`|Obbligatorio. Espressione che verrà valutata e assegnata alla variabile specificata.|  
  
## <a name="remarks"></a>Commenti  
 La `Let` clausola consente di calcolare i valori per ogni risultato della query e di farvi riferimento tramite un alias. L'alias può essere utilizzato in altre clausole, ad esempio la `Where` clausola. La `Let` clausola consente di creare un'istruzione di query più semplice da leggere poiché è possibile specificare un alias per una clausola Expression inclusa nella query e sostituire l'alias ogni volta che viene utilizzata la clausola Expression.  
  
 È possibile includere un numero qualsiasi `variable` di `expression` assegnazioni e nella `Let` clausola. Separare ogni assegnazione con una virgola (,).  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene usata la `Let` clausola per calcolare uno sconto del 10% sui prodotti.  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](index.md)
- [Clausola SELECT](select-clause.md)
- [Clausola from](from-clause.md)
- [Clausola WHERE](where-clause.md)
