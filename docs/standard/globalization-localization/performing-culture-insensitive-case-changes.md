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
# <a name="performing-culture-insensitive-case-changes"></a><span data-ttu-id="d226c-102">Esecuzione di modifiche di maiuscole e minuscole indipendenti dalle impostazioni cultura</span><span class="sxs-lookup"><span data-stu-id="d226c-102">Performing Culture-Insensitive Case Changes</span></span>
<span data-ttu-id="d226c-103">Il <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, e <xref:System.Char.ToLower%2A?displayProperty=nameWithType> forniscono overload che accettano parametri.</span><span class="sxs-lookup"><span data-stu-id="d226c-103">The <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, and <xref:System.Char.ToLower%2A?displayProperty=nameWithType> methods provide overloads that do not accept any parameters.</span></span> <span data-ttu-id="d226c-104">Per impostazione predefinita, questi overload senza parametri eseguono modifiche in base al valore del <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d226c-104">By default, these overloads without parameters perform case changes based on the value of the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d226c-105">Questo produce risultati tra maiuscole e minuscole che possono variare in base alle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="d226c-105">This produces case-sensitive results that can vary by culture.</span></span> <span data-ttu-id="d226c-106">Per indicare chiaramente se si desidera case modifiche delle impostazioni cultura o indipendenti dalle impostazioni cultura, è opportuno utilizzare l'overload di questi metodi che è necessario specificare in modo esplicito un `culture` parametro.</span><span class="sxs-lookup"><span data-stu-id="d226c-106">To make it clear whether you want case changes to be culture-sensitive or culture-insensitive, you should use the overloads of these methods that require you to explicitly specify a `culture` parameter.</span></span> <span data-ttu-id="d226c-107">Per modifiche delle impostazioni cultura, specificare `CultureInfo.CurrentCulture` per il `culture` parametro.</span><span class="sxs-lookup"><span data-stu-id="d226c-107">For culture-sensitive case changes, specify `CultureInfo.CurrentCulture` for the `culture` parameter.</span></span> <span data-ttu-id="d226c-108">Per le modifiche indipendenti dalle impostazioni cultura, specificare `CultureInfo.InvariantCulture` per il `culture` parametro.</span><span class="sxs-lookup"><span data-stu-id="d226c-108">For culture-insensitive case changes, specify `CultureInfo.InvariantCulture` for the `culture` parameter.</span></span>  
  
 <span data-ttu-id="d226c-109">Spesso, le stringhe vengono convertite in un caso standard per abilitare la ricerca semplice in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="d226c-109">Often, strings are converted to a standard case to enable easier lookup later.</span></span> <span data-ttu-id="d226c-110">Quando le stringhe vengono utilizzate in questo modo, è necessario specificare `CultureInfo.InvariantCulture` per il `culture` parametro, perché il valore di <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> può essere modificato tra il momento in caso di modifica e l'ora in cui viene eseguita la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d226c-110">When strings are used in this way, you should specify `CultureInfo.InvariantCulture` for the `culture` parameter, because the value of <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> can potentially change between the time that the case is changed and the time that the lookup occurs.</span></span>  
  
 <span data-ttu-id="d226c-111">Se una decisione relativa alla sicurezza è basato su un'operazione di modifica di maiuscole, l'operazione deve essere indipendente dalle impostazioni cultura per assicurarsi che il risultato non è influenzato dal valore di `CultureInfo.CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="d226c-111">If a security decision is based on a case change operation, the operation should be culture-insensitive to ensure that the result is not affected by the value of `CultureInfo.CurrentCulture`.</span></span> <span data-ttu-id="d226c-112">Vedere la sezione "Stringa confronti che usa il corrente delle impostazioni cultura" il [procedure consigliate per l'uso di stringhe](../../../docs/standard/base-types/best-practices-strings.md) articolo per un esempio che illustra le operazioni di stringa come impostazioni cultura può produrre risultati incoerenti.</span><span class="sxs-lookup"><span data-stu-id="d226c-112">See the "String Comparisons that Use the Current Culture" section of the [Best Practices for Using Strings](../../../docs/standard/base-types/best-practices-strings.md) article for an example that demonstrates how culture-sensitive string operations can produce inconsistent results.</span></span>  
  
## <a name="using-the-stringtoupper-and-stringtolower-methods"></a><span data-ttu-id="d226c-113">Utilizzo di String. ToUpper e String. ToLower metodi</span><span class="sxs-lookup"><span data-stu-id="d226c-113">Using the String.ToUpper and String.ToLower Methods</span></span>  
 <span data-ttu-id="d226c-114">Per maggiore chiarezza del codice, è consigliabile utilizzare sempre l'overload di `String.ToUpper` e `String.ToLower` metodi che consentono di specificare un `culture` parametro in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="d226c-114">For code clarity, it is recommended that you always use overloads of the `String.ToUpper` and `String.ToLower` methods that allow you to specify a `culture` parameter explicitly.</span></span> <span data-ttu-id="d226c-115">Ad esempio, il codice seguente esegue una ricerca dell'identificatore.</span><span class="sxs-lookup"><span data-stu-id="d226c-115">For example, the following code performs an identifier lookup.</span></span> <span data-ttu-id="d226c-116">Il `key.ToLower` l'operazione è la distinzione delle impostazioni cultura per impostazione predefinita, ma questo comportamento non è chiara dalla lettura del codice.</span><span class="sxs-lookup"><span data-stu-id="d226c-116">The `key.ToLower` operation is culture-sensitive by default, but this behavior is not clear from reading the code.</span></span>  
  
### <a name="example"></a><span data-ttu-id="d226c-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="d226c-117">Example</span></span>  
  
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
  
 <span data-ttu-id="d226c-118">Se si desidera che il `key.ToLower` operazione sia indipendente dalle impostazioni cultura, è necessario modificare l'esempio precedente come indicato di seguito per utilizzare in modo esplicito il `CultureInfo.InvariantCulture` quando si modifica il case.</span><span class="sxs-lookup"><span data-stu-id="d226c-118">If you want the `key.ToLower` operation to be culture-insensitive, you should change the preceding example as follows to explicitly use the `CultureInfo.InvariantCulture` when changing the case.</span></span>  
  
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
  
## <a name="using-the-chartoupper-and-chartolower-methods"></a><span data-ttu-id="d226c-119">Utilizzando il Char. ToUpper e Char. ToLower metodi</span><span class="sxs-lookup"><span data-stu-id="d226c-119">Using the Char.ToUpper and Char.ToLower Methods</span></span>  
 <span data-ttu-id="d226c-120">Sebbene il `Char.ToUpper` e `Char.ToLower` metodi hanno le stesse caratteristiche come il `String.ToUpper` e `String.ToLower` metodi, le uniche impostazioni cultura su cui hanno effetto sono Turco (Turchia) e Azero (alfabeto latino, Azerbaijan).</span><span class="sxs-lookup"><span data-stu-id="d226c-120">Although the `Char.ToUpper` and `Char.ToLower` methods have the same characteristics as the `String.ToUpper` and `String.ToLower` methods, the only cultures that are affected are Turkish (Turkey) and Azerbaijani (Latin, Azerbaijan).</span></span> <span data-ttu-id="d226c-121">Queste sono le uniche due lingue con differenze di maiuscole e minuscole a carattere singolo.</span><span class="sxs-lookup"><span data-stu-id="d226c-121">These are the only two cultures with single-character casing differences.</span></span> <span data-ttu-id="d226c-122">Per informazioni dettagliate su questo mapping di maiuscole e minuscole univoco, vedere la sezione "Maiuscole e minuscole" dell'argomento della classe <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="d226c-122">For more details about this unique case mapping, see the "Casing" section in the <xref:System.String> class topic.</span></span> <span data-ttu-id="d226c-123">Per maggiore chiarezza del codice e per garantire risultati coerenti, è consigliabile utilizzare sempre l'overload di questi metodi che consentono di specificare in modo esplicito un `culture` parametro.</span><span class="sxs-lookup"><span data-stu-id="d226c-123">For code clarity and to ensure consistent results, it is recommended that you always use the overloads of these methods that allow you to explicitly specify a `culture` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d226c-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d226c-124">See Also</span></span>  
 <xref:System.String.ToUpper%2A?displayProperty=nameWithType>  
 <xref:System.String.ToLower%2A?displayProperty=nameWithType>  
 <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>  
 <xref:System.Char.ToLower%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="d226c-125">Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura</span><span class="sxs-lookup"><span data-stu-id="d226c-125">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
