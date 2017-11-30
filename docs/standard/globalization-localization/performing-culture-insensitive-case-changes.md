---
title: Esecuzione di modifiche di maiuscole e minuscole indipendenti dalle impostazioni cultura
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- String.ToLower method
- culture, case sensitivity
- Char.ToLower method
- case, changing in culture-insensitive strings
- Char.ToUpper method
- culture-insensitive string operations, case changes
- String.ToUpper method
- culture parameter
ms.assetid: 822d551c-c69a-4191-82f4-183d82c9179c
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c500b882c335572b8b458ba515b282e9f5362b85
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="performing-culture-insensitive-case-changes"></a>Esecuzione di modifiche di maiuscole e minuscole indipendenti dalle impostazioni cultura
Il <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, e <xref:System.Char.ToLower%2A?displayProperty=nameWithType> forniscono overload che accettano parametri. Per impostazione predefinita, questi overload senza parametri eseguono modifiche in base al valore del <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>. Questo produce risultati tra maiuscole e minuscole che possono variare in base alle impostazioni cultura. Per indicare chiaramente se si desidera case modifiche delle impostazioni cultura o indipendenti dalle impostazioni cultura, è opportuno utilizzare l'overload di questi metodi che è necessario specificare in modo esplicito un `culture` parametro. Per modifiche delle impostazioni cultura, specificare `CultureInfo.CurrentCulture` per il `culture` parametro. Per le modifiche indipendenti dalle impostazioni cultura, specificare `CultureInfo.InvariantCulture` per il `culture` parametro.  
  
 Spesso, le stringhe vengono convertite in un caso standard per abilitare la ricerca semplice in un secondo momento. Quando le stringhe vengono utilizzate in questo modo, è necessario specificare `CultureInfo.InvariantCulture` per il `culture` parametro, perché il valore di <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> può essere modificato tra il momento in caso di modifica e l'ora in cui viene eseguita la ricerca.  
  
 Se una decisione relativa alla sicurezza è basato su un'operazione di modifica di maiuscole, l'operazione deve essere indipendente dalle impostazioni cultura per assicurarsi che il risultato non è influenzato dal valore di `CultureInfo.CurrentCulture`. Vedere la sezione "Stringa confronti che usa il corrente delle impostazioni cultura" il [procedure consigliate per l'uso di stringhe](../../../docs/standard/base-types/best-practices-strings.md) articolo per un esempio che illustra le operazioni di stringa come impostazioni cultura può produrre risultati incoerenti.  
  
## <a name="using-the-stringtoupper-and-stringtolower-methods"></a>Utilizzo di String. ToUpper e String. ToLower metodi  
 Per maggiore chiarezza del codice, è consigliabile utilizzare sempre l'overload di `String.ToUpper` e `String.ToLower` metodi che consentono di specificare un `culture` parametro in modo esplicito. Ad esempio, il codice seguente esegue una ricerca dell'identificatore. Il `key.ToLower` l'operazione è la distinzione delle impostazioni cultura per impostazione predefinita, ma questo comportamento non è chiara dalla lettura del codice.  
  
### <a name="example"></a>Esempio  
  
```vb  
Shared Function LookupKey(key As String) As Object  
   Return internalHashtable(key.ToLower())  
End Function  
```  
  
```csharp  
static object LookupKey(string key)   
{  
    return internalHashtable[key.ToLower()];  
}  
```  
  
 Se si desidera che il `key.ToLower` operazione sia indipendente dalle impostazioni cultura, è necessario modificare l'esempio precedente come indicato di seguito per utilizzare in modo esplicito il `CultureInfo.InvariantCulture` quando si modifica il case.  
  
```vb  
Shared Function LookupKey(key As String) As Object  
    Return internalHashtable(key.ToLower(CultureInfo.InvariantCulture))  
End Function  
```  
  
```csharp  
static object LookupKey(string key)   
{  
    return internalHashtable[key.ToLower(CultureInfo.InvariantCulture)];  
}  
```  
  
## <a name="using-the-chartoupper-and-chartolower-methods"></a>Utilizzando il Char. ToUpper e Char. ToLower metodi  
 Sebbene il `Char.ToUpper` e `Char.ToLower` metodi hanno le stesse caratteristiche come il `String.ToUpper` e `String.ToLower` metodi, le uniche impostazioni cultura su cui hanno effetto sono Turco (Turchia) e Azero (alfabeto latino, Azerbaijan). Queste sono le uniche due lingue con differenze di maiuscole e minuscole a carattere singolo. Per informazioni dettagliate su questo mapping di maiuscole e minuscole univoco, vedere la sezione "Maiuscole e minuscole" dell'argomento della classe <xref:System.String>. Per maggiore chiarezza del codice e per garantire risultati coerenti, è consigliabile utilizzare sempre l'overload di questi metodi che consentono di specificare in modo esplicito un `culture` parametro.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.String.ToUpper%2A?displayProperty=nameWithType>  
 <xref:System.String.ToLower%2A?displayProperty=nameWithType>  
 <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>  
 <xref:System.Char.ToLower%2A?displayProperty=nameWithType>  
 [Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
