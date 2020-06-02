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
ms.openlocfilehash: 79ff899e2964ae2c1e90b7178616c612dddf6d86
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287506"
---
# <a name="performing-culture-insensitive-string-operations"></a>Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura
Per la maggior parte, i metodi di .NET Framework che eseguono operazioni sulle stringhe dipendenti dalle impostazioni cultura forniscono, per impostazione predefinita, overload dei metodi che consentono di specificare in modo esplicito le impostazioni cultura da usare mediante il passaggio di un parametro <xref:System.Globalization.CultureInfo>. Questi overload consentono di eliminare le variazioni legate alle impostazioni cultura in mapping tra maiuscole e minuscole e regole di ordinamento e garantiscono risultati indipendenti dalle impostazioni cultura.  
  
 In questa sezione vengono forniti gli argomenti elencati di seguito, in cui viene illustrato come eseguire operazioni sulle stringhe indipendenti dalle impostazioni cultura usando metodi .NET Framework che per impostazione predefinita sono dipendenti dalle impostazioni cultura.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Esecuzione di confronti di stringhe indipendenti dalle impostazioni cultura](performing-culture-insensitive-string-comparisons.md)  
 Descrive come usare i metodi <xref:System.String.Compare%2A?displayProperty=nameWithType> e <xref:System.String.CompareTo%2A?displayProperty=nameWithType> per eseguire confronti tra stringhe indipendenti dalle impostazioni cultura.  
  
 [Esecuzione di modifiche di maiuscole e minuscole indipendenti dalle impostazioni cultura](performing-culture-insensitive-case-changes.md)  
 Descrive come usare i metodi <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, e <xref:System.Char.ToLower%2A?displayProperty=nameWithType> per eseguire modifiche di maiuscole e minuscole indipendenti dalle impostazioni cultura.  
  
 [Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura nelle raccolte](performing-culture-insensitive-string-operations-in-collections.md)  
 Descrive come usare <xref:System.Collections.CaseInsensitiveComparer>, <xref:System.Collections.CaseInsensitiveHashCodeProvider> (classe), <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> e <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> per eseguire operazioni indipendenti dalle impostazioni cultura nelle raccolte.  
  
 [Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura nelle matrici](performing-culture-insensitive-string-operations-in-arrays.md)  
 Descrive come usare i metodi <xref:System.Array.Sort%2A?displayProperty=nameWithType> e <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> per eseguire operazioni indipendenti dalle impostazioni cultura nelle matrici.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Operazioni sulle stringhe indipendenti dalle impostazioni cultura](culture-insensitive-string-operations.md)  
 Vengono descritti i motivi per cui è opportuno tenere in considerazione le impostazioni cultura in occasione dell'esecuzione di operazioni sulle stringhe e vengono fornite indicazioni sui casi in cui devono essere eseguite operazioni dipendenti dalle impostazioni cultura o operazioni indipendenti dalle impostazioni cultura.

## <a name="see-also"></a>Vedere anche

- [Sorting Weight Tables (for .NET on Windows systems)](https://www.microsoft.com/download/details.aspx?id=10921) (Tabelle di ordinamento spessore - Per .NET in sistemi Windows)
- [Default Unicode Collation Element Table (for .NET Core on Linux and macOS)](https://www.unicode.org/Public/UCA/latest/allkeys.txt) (Tabella degli elementi delle regole di confronto Unicode predefinite - Per .NET Core in Linux e MacOS)
