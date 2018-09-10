---
title: Ottenere una query da un metodo
description: Come ottenere una query.
ms.date: 11/30/2016
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.openlocfilehash: 1c5fa534f3f39f8201d93b986e687d85bb303736
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510787"
---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a>Procedura: ottenere una query da un metodo (Guida per programmatori C#)
In questo esempio viene illustrato come ottenere una query da un metodo come valore restituito e come parametro `out`.  
  
 Gli oggetti di query sono componibili, vale a dire che è possibile ottenere una query da un metodo. Gli oggetti che rappresentano le query non memorizzano la raccolta risultante, ma piuttosto i passaggi da eseguire per ottenere i risultati quando necessario. Il vantaggio di ottenere oggetti query dai metodi è che gli oggetti possono essere ulteriormente composti o modificati. Di conseguenza, qualsiasi valore restituito o parametro `out` di un metodo che restituisce una query deve contenere anche quel tipo. Se un metodo materializza una query in un oggetto <xref:System.Collections.Generic.List%601> concreto o un tipo <xref:System.Array>, si ritiene che restituisca i risultati della query anziché la query stessa. Una variabile di query che viene restituita da un metodo può ancora essere composta o modificata.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente il primo metodo restituisce una query come valore restituito e il secondo metodo restituisce una query come parametro `out`. Notare che in entrambi i casi è una query che viene restituita, non i risultati della query.  
  
 [!code-csharp[csProgGuideLINQ#80](~/samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]  

## <a name="see-also"></a>Vedere anche

- [LINQ (Language-Integrated Query)](index.md)
