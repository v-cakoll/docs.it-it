---
title: Matrici
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
caps.latest.revision: 18
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 54f5d68a343f473c67484e9e806551eb115bac36
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="arrays"></a>Matrici
**✓ SI** preferire l'utilizzo di raccolte sulle matrici nelle API pubbliche. Il [raccolte](../../../docs/standard/design-guidelines/guidelines-for-collections.md) sezione vengono fornite informazioni dettagliate su come scegliere tra le raccolte e matrici.  
  
 **X non** utilizzare campi di matrice di sola lettura. Il campo è di sola lettura e non può essere modificato, ma gli elementi nella matrice possono essere modificati.  
  
 **✓ Provare a** utilizzando matrici di matrici anziché le matrici multidimensionali.  
  
 Una matrice di matrici è una matrice con gli elementi che sono anche le matrici. Le matrici che costituiscono gli elementi possono presentare dimensioni diverse, la spazio inutilizzato sarà inferiore per alcuni set di dati (ad esempio, matrice di tipo sparse) rispetto a matrici multidimensionali. Inoltre, CLR consente di ottimizzare operazioni sugli indici su matrici di matrici, in modo che potrebbe presentare migliori prestazioni di runtime in alcuni scenari.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Array>  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
 [Linee guida per l'uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
