---
title: Partizionamento dei dati (C#)
ms.date: 07/20/2015
ms.assetid: 2a5c507b-fe22-443c-a768-dec7f9ec568d
ms.openlocfilehash: d9330e9973b2f25903e1f81a7296362e2a7c756b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69591586"
---
# <a name="partitioning-data-c"></a>Partizionamento dei dati (C#)
Il partizionamento in LINQ è l'operazione di divisione di una sequenza di input in due sezioni senza ridisposizione degli elementi e la successiva restituzione di una delle sezioni.  
  
 La figura seguente illustra i risultati di tre diverse operazioni di partizionamento in una sequenza di caratteri. La prima operazione restituisce i primi tre elementi nella sequenza. La seconda operazione ignora i primi tre elementi e restituisce gli elementi rimanenti. La terza operazione ignora i primi due elementi nella sequenza e restituisce i tre elementi successivi.  
  
 ![Figura che illustra tre operazioni di partizionamento LINQ.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 Nella sezione seguente sono elencati i metodi degli operatori di query standard che eseguono la partizione delle sequenze.  
  
## <a name="operators"></a>Operatori  
  
|Nome operatore|Descrizione|Sintassi di espressione della query C#|Altre informazioni|  
|-------------------|-----------------|---------------------------------|----------------------|  
|Skip|Ignora gli elementi fino a una posizione specificata in una sequenza.|Non applicabile.|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|SkipWhile|Ignora gli elementi in base a una funzione di predicato fino a quando un elemento non soddisfa la condizione.|Non applicabile.|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|Take|Accetta gli elementi fino a una posizione specificata in una sequenza.|Non applicabile.|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|TakeWhile|Accetta gli elementi in base a una funzione di predicato fino a quando un elemento non soddisfa la condizione.|Non applicabile.|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- [Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Panoramica degli operatori di query standard)
