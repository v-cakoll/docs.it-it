---
title: Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura nelle matrici
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- culture-insensitive string operations, in arrays
- arrays [.NET Framework], culture-insensitive string operations
- comparer parameter
ms.assetid: f12922e1-6234-4165-8896-63f0653ab478
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22815b5ab993b36bc8bcb91f89f346cb6d812e19
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44251693"
---
# <a name="performing-culture-insensitive-string-operations-in-arrays"></a>Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura nelle matrici
Per impostazione predefinita, gli overload dei metodi <xref:System.Array.Sort%2A?displayProperty=nameWithType> e <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> consentono di eseguire ordinamenti dipendenti dalle impostazioni cultura tramite la proprietà <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>. I risultati dipendenti dalle impostazioni cultura restituiti da questi metodi possono variare in base a tali impostazioni a causa dei diversi tipi di ordinamento. Per eliminare il comportamento dipendente dalle impostazioni cultura, usare uno degli overload del metodo che accetta il parametro `comparer`. Il parametro `comparer` specifica l'implementazione di <xref:System.Collections.IComparer> da usare quando si confrontano gli elementi nella matrice. Per il parametro specificare una classe di operatori di confronto invariabili personalizzati che usi <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Un esempio di classe di operatori di confronto invariabili viene fornito nell'argomento secondario "Utilizzo della classe SortedList" dell'argomento [Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura nelle raccolte](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md).  
  
 **Nota** Il passaggio di**CultureInfo.InvariantCulture** a un metodo di confronto comporta l'esecuzione di un confronto non basato sulle impostazioni di cultura. Non viene tuttavia eseguito un confronto non linguistico, ad esempio per percorsi di file, chiavi del Registro di sistema e variabili di ambiente e non sono supportate le decisioni relative alla sicurezza basate sul risultato del confronto. Per un confronto non linguistico o per il supporto delle decisioni relative alla sicurezza basate sul risultato, l'applicazione deve utilizzare un metodo di confronto che accetti un valore <xref:System.StringComparison>. L'applicazione deve quindi passare <xref:System.StringComparison.Ordinal>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
- <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>  
- <xref:System.Collections.IComparer>  
- [Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
