---
title: Matrici
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c957d4336527de8c11b763c31c1fdf0015b675b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="arrays"></a>Matrici
**✓ SI** preferire l'utilizzo di raccolte sulle matrici nelle API pubbliche. Il [raccolte](../../../docs/standard/design-guidelines/guidelines-for-collections.md) sezione vengono fornite informazioni dettagliate su come scegliere tra le raccolte e matrici.  
  
 **X non** utilizzare campi di matrice di sola lettura. Il campo è di sola lettura e non può essere modificato, ma gli elementi nella matrice possono essere modificati.  
  
 **Provare a ✓** utilizzando le matrici di matrici anziché le matrici multidimensionali.  
  
 Una matrice di matrici è una matrice con gli elementi che sono anche le matrici. Le matrici che costituiscono gli elementi possono presentare dimensioni diverse, la spazio inutilizzato sarà inferiore per alcuni set di dati (ad esempio, matrice di tipo sparse) rispetto a matrici multidimensionali. Inoltre, CLR consente di ottimizzare operazioni sugli indici su matrici di matrici, in modo che potrebbe presentare migliori prestazioni di runtime in alcuni scenari.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Array>  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Linee guida di utilizzo](../../../docs/standard/design-guidelines/usage-guidelines.md)
