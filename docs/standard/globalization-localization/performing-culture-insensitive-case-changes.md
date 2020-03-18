---
title: Esecuzione di modifiche di maiuscole e minuscole indipendenti dalle impostazioni cultura
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 7b2dee03619e24c5a2845699a06e88abab0c594b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160131"
---
# <a name="performing-culture-insensitive-case-changes"></a>Esecuzione di modifiche di maiuscole e minuscole indipendenti dalle impostazioni cultura
I metodi <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, e <xref:System.Char.ToLower%2A?displayProperty=nameWithType> forniscono overload che non accettano parametri. Per impostazione predefinita, questi overload senza parametri eseguono modifiche di maiuscole e minuscole in base al valore di <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>. Ciò produce risultati con distinzione tra maiuscole e minuscole che possono variare in base alle impostazioni cultura. Per definire modifiche di maiuscole e minuscole dipendenti o meno dalle impostazioni cultura, è consigliabile usare gli overload di questi metodi che richiedono di specificare in modo esplicito un parametro `culture`. Per definire modifiche di maiuscole e minuscole dipendenti dalle impostazioni cultura, specificare `CultureInfo.CurrentCulture` per il parametro `culture`. Per definire modifiche indipendenti dalle impostazioni cultura, specificare `CultureInfo.InvariantCulture` per il parametro `culture`.  
  
 La combinazione di maiuscole e minuscole nelle stringhe viene spesso convertita in base a un criterio standard per abilitare e semplificare la ricerca in un secondo momento. Quando le stringhe vengono usate in questo modo, è necessario specificare `CultureInfo.InvariantCulture` per il parametro `culture`, perché è possibile che il valore di <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> vari tra il momento in cui si verifica la modifica di maiuscole e minuscole e il momento in cui viene eseguita la ricerca.  
  
 Se una decisione relativa alla sicurezza è basata su un'operazione di modifica di maiuscole e minuscole, è necessario che l'operazione sia indipendente dalle impostazioni cultura in modo che il risultato non venga influenzato dal valore di `CultureInfo.CurrentCulture`. Per un esempio in cui viene illustrato il modo in cui le operazioni su stringhe dipendenti dalle impostazioni cultura possono comportare risultati non coerenti, vedere la sezione relativa ai confronti di stringhe in cui vengono utilizzate le impostazioni cultura correnti nell'articolo [Best Practices for Using Strings](../../../docs/standard/base-types/best-practices-strings.md).  
  
## <a name="using-the-stringtoupper-and-stringtolower-methods"></a>Uso dei metodi String.ToUpper e String.ToLower  
 Per ottenere una maggiore chiarezza del codice, è consigliabile usare sempre gli overload dei metodi `String.ToUpper` e `String.ToLower`, che consentono di specificare un parametro `culture` in modo esplicito. Nel codice seguente, ad esempio, viene eseguita una ricerca dell'identificatore. L'operazione `key.ToLower` non dipende dalle impostazioni cultura per impostazione predefinita, ma questo comportamento non è evidente da una lettura del codice.  
  
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
  
 Se si desidera che l'operazione `key.ToLower` non dipenda dalle impostazioni cultura, è necessario modificare l'esempio precedente come indicato di seguito per usare in modo esplicito `CultureInfo.InvariantCulture` in caso di modifica di maiuscole/minuscole.  
  
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
  
## <a name="using-the-chartoupper-and-chartolower-methods"></a>Uso dei metodi Char.ToUpper e Char.ToLower  
 Sebbene i metodi `Char.ToUpper` e `Char.ToLower` abbiano le stesse caratteristiche dei metodi `String.ToUpper` e `String.ToLower`, le uniche impostazioni cultura su cui hanno effetto sono Turco (Turchia) e Azerbaigiano (alfabeto latino, Azerbaigian). Queste sono le uniche due impostazioni cultura con differenze di maiuscole e minuscole a carattere singolo. Per informazioni dettagliate su questo mapping di maiuscole e minuscole univoco, vedere la sezione "Maiuscole e minuscole" dell'argomento della classe <xref:System.String>. Per maggiore chiarezza del codice e per garantire risultati coerenti, è consigliabile usare sempre gli overload di questi metodi che consentono di specificare in modo esplicito un parametro `culture`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.String.ToUpper%2A?displayProperty=nameWithType>
- <xref:System.String.ToLower%2A?displayProperty=nameWithType>
- <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>
- <xref:System.Char.ToLower%2A?displayProperty=nameWithType>
- [Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
