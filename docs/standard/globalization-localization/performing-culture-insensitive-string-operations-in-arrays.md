---
title: Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura nelle matrici
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- culture-insensitive string operations, in arrays
- arrays [.NET Framework], culture-insensitive string operations
- comparer parameter
ms.assetid: f12922e1-6234-4165-8896-63f0653ab478
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1b4e040ed379cdbf43fbe8b2c4379fdd4dc781f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="performing-culture-insensitive-string-operations-in-arrays"></a>Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura nelle matrici
Esegue l'overload di <xref:System.Array.Sort%2A?displayProperty=nameWithType> e <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> metodi eseguono ordinamenti predefinito utilizzando il <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> proprietà. Le impostazioni cultura restituite da questi metodi possono variare dalle impostazioni cultura a causa delle differenze nell'ordinamento. Per eliminare il comportamento delle impostazioni cultura, utilizzare uno degli overload del metodo che accetta un `comparer` parametro. Il `comparer` parametro specifica il <xref:System.Collections.IComparer> implementazione da usare quando si confrontano gli elementi nella matrice. Per il parametro, specificare una classe che utilizza <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Viene fornito un esempio di una classe nell'argomento secondario di "Utilizzo della classe SortedList" il [esecuzione di operazioni di stringa indipendenti dalle impostazioni cultura nelle raccolte](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) argomento.  
  
 **Nota** passando **CultureInfo. InvariantCulture** per un confronto metodo viene eseguito un confronto senza distinzione di impostazioni cultura. Non viene tuttavia eseguito un confronto non linguistico, ad esempio per percorsi di file, chiavi del Registro di sistema e variabili di ambiente e non sono supportate le decisioni relative alla sicurezza basate sul risultato del confronto. Per un confronto non linguistico o il supporto per le decisioni di sicurezza basata sui risultati, l'applicazione deve utilizzare un metodo di confronto che accetta un <xref:System.StringComparison> valore. L'applicazione deve passare quindi <xref:System.StringComparison.Ordinal>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>  
 <xref:System.Collections.IComparer>  
 [Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
