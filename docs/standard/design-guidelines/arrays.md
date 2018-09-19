---
title: Matrici
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ac7e28c3172f2ed68d402e1d04a1664644c7f25
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2018
ms.locfileid: "46324711"
---
# <a name="arrays"></a>Matrici
**✓ DO** preferire l'utilizzo di raccolte sulle matrici nelle API pubbliche. Il [raccolte](../../../docs/standard/design-guidelines/guidelines-for-collections.md) sezione vengono fornite informazioni dettagliate su come scegliere tra le raccolte e matrici.  
  
 **X DO NOT** utilizzare campi di matrice di sola lettura. Il campo stesso è di sola lettura e non può essere modificato, ma gli elementi della matrice possono essere modificati.  
  
 **✓ CONSIDER** utilizzando matrici di matrici anziché le matrici multidimensionali.  
  
 Una matrice di matrici è una matrice con elementi che sono anche le matrici. Le matrici che costituiscono gli elementi possono essere di dimensioni diverse, spazio inutilizzato sarà inferiore per alcuni set di dati (ad esempio, matrice di tipo sparse) rispetto a matrici multidimensionali. Inoltre, CLR ottimizza le operazioni di indice in matrici di matrici, in modo che potrebbe presentare prestazioni di runtime migliori in alcuni scenari.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Array>  
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)  
- [Linee guida per l'uso](../../../docs/standard/design-guidelines/usage-guidelines.md)
