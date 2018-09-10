---
title: Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura
ms.date: 08/22/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- case mappings
- custom case mappings
- culture, custom sorting rules
- custom sorting rules
- culture-insensitive string operations, options for performing
- culture, custom case mappings
- culture-insensitive string operations, method overloads
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 748b4170e9e4c0df048c542d06bcb64a56ccf677
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44199947"
---
# <a name="performing-culture-insensitive-string-operations"></a>Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura
Per la maggior parte, i metodi di .NET Framework che eseguono operazioni sulle stringhe dipendenti dalle impostazioni cultura forniscono, per impostazione predefinita, overload dei metodi che consentono di specificare in modo esplicito le impostazioni cultura da usare mediante il passaggio di un parametro <xref:System.Globalization.CultureInfo>. Questi overload consentono di eliminare le variazioni legate alle impostazioni cultura in mapping tra maiuscole e minuscole e regole di ordinamento e garantiscono risultati indipendenti dalle impostazioni cultura.  
  
 In questa sezione vengono forniti gli argomenti elencati di seguito, in cui viene illustrato come eseguire operazioni sulle stringhe indipendenti dalle impostazioni cultura usando metodi .NET Framework che per impostazione predefinita sono dipendenti dalle impostazioni cultura.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Esecuzione di confronti di stringhe indipendenti dalle impostazioni cultura](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)  
 Descrive come usare i metodi <xref:System.String.Compare%2A?displayProperty=nameWithType> e <xref:System.String.CompareTo%2A?displayProperty=nameWithType> per eseguire confronti tra stringhe indipendenti dalle impostazioni cultura.  
  
 [Esecuzione di modifiche di maiuscole e minuscole indipendenti dalle impostazioni cultura](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)  
 Descrive come usare i metodi <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, e <xref:System.Char.ToLower%2A?displayProperty=nameWithType> per eseguire modifiche di maiuscole e minuscole indipendenti dalle impostazioni cultura.  
  
 [Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura nelle raccolte](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)  
 Descrive come usare <xref:System.Collections.CaseInsensitiveComparer>, <xref:System.Collections.CaseInsensitiveHashCodeProvider> (classe), <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> e <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> per eseguire operazioni indipendenti dalle impostazioni cultura nelle raccolte.  
  
 [Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura nelle matrici](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)  
 Descrive come usare i metodi <xref:System.Array.Sort%2A?displayProperty=nameWithType> e <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> per eseguire operazioni indipendenti dalle impostazioni cultura nelle matrici.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Operazioni sulle stringhe indipendenti dalle impostazioni cultura](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 Vengono descritti i motivi per cui è opportuno tenere in considerazione le impostazioni cultura in occasione dell'esecuzione di operazioni sulle stringhe e vengono fornite indicazioni sui casi in cui devono essere eseguite operazioni dipendenti dalle impostazioni cultura o operazioni indipendenti dalle impostazioni cultura.

## <a name="see-also"></a>Vedere anche

- [Sorting Weight Tables](https://www.microsoft.com/en-us/download/details.aspx?id=10921)
