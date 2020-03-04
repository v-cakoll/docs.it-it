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
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160131"
---
# <a name="performing-culture-insensitive-case-changes"></a><span data-ttu-id="f4b5e-102">Esecuzione di modifiche di maiuscole e minuscole indipendenti dalle impostazioni cultura</span><span class="sxs-lookup"><span data-stu-id="f4b5e-102">Performing Culture-Insensitive Case Changes</span></span>
<span data-ttu-id="f4b5e-103">I metodi <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, e <xref:System.Char.ToLower%2A?displayProperty=nameWithType> forniscono overload che non accettano parametri.</span><span class="sxs-lookup"><span data-stu-id="f4b5e-103">The <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, and <xref:System.Char.ToLower%2A?displayProperty=nameWithType> methods provide overloads that do not accept any parameters.</span></span> <span data-ttu-id="f4b5e-104">Per impostazione predefinita, questi overload senza parametri eseguono modifiche di maiuscole e minuscole in base al valore di <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f4b5e-104">By default, these overloads without parameters perform case changes based on the value of the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f4b5e-105">Ciò produce risultati con distinzione tra maiuscole e minuscole che possono variare in base alle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="f4b5e-105">This produces case-sensitive results that can vary by culture.</span></span> <span data-ttu-id="f4b5e-106">Per definire modifiche di maiuscole e minuscole dipendenti o meno dalle impostazioni cultura, è consigliabile usare gli overload di questi metodi che richiedono di specificare in modo esplicito un parametro `culture`.</span><span class="sxs-lookup"><span data-stu-id="f4b5e-106">To make it clear whether you want case changes to be culture-sensitive or culture-insensitive, you should use the overloads of these methods that require you to explicitly specify a `culture` parameter.</span></span> <span data-ttu-id="f4b5e-107">Per definire modifiche di maiuscole e minuscole dipendenti dalle impostazioni cultura, specificare `CultureInfo.CurrentCulture` per il parametro `culture`.</span><span class="sxs-lookup"><span data-stu-id="f4b5e-107">For culture-sensitive case changes, specify `CultureInfo.CurrentCulture` for the `culture` parameter.</span></span> <span data-ttu-id="f4b5e-108">Per definire modifiche indipendenti dalle impostazioni cultura, specificare `CultureInfo.InvariantCulture` per il parametro `culture`.</span><span class="sxs-lookup"><span data-stu-id="f4b5e-108">For culture-insensitive case changes, specify `CultureInfo.InvariantCulture` for the `culture` parameter.</span></span>  
  
 <span data-ttu-id="f4b5e-109">La combinazione di maiuscole e minuscole nelle stringhe viene spesso convertita in base a un criterio standard per abilitare e semplificare la ricerca in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="f4b5e-109">Often, strings are converted to a standard case to enable easier lookup later.</span></span> <span data-ttu-id="f4b5e-110">Quando le stringhe vengono usate in questo modo, è necessario specificare `CultureInfo.InvariantCulture` per il parametro `culture`, perché è possibile che il valore di <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> vari tra il momento in cui si verifica la modifica di maiuscole e minuscole e il momento in cui viene eseguita la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f4b5e-110">When strings are used in this way, you should specify `CultureInfo.InvariantCulture` for the `culture` parameter, because the value of <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> can potentially change between the time that the case is changed and the time that the lookup occurs.</span></span>  
  
 <span data-ttu-id="f4b5e-111">Se una decisione relativa alla sicurezza è basata su un'operazione di modifica di maiuscole e minuscole, è necessario che l'operazione sia indipendente dalle impostazioni cultura in modo che il risultato non venga influenzato dal valore di `CultureInfo.CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="f4b5e-111">If a security decision is based on a case change operation, the operation should be culture-insensitive to ensure that the result is not affected by the value of `CultureInfo.CurrentCulture`.</span></span> <span data-ttu-id="f4b5e-112">Per un esempio in cui viene illustrato il modo in cui le operazioni su stringhe dipendenti dalle impostazioni cultura possono comportare risultati non coerenti, vedere la sezione relativa ai confronti di stringhe in cui vengono utilizzate le impostazioni cultura correnti nell'articolo [Best Practices for Using Strings](../../../docs/standard/base-types/best-practices-strings.md).</span><span class="sxs-lookup"><span data-stu-id="f4b5e-112">See the "String Comparisons that Use the Current Culture" section of the [Best Practices for Using Strings](../../../docs/standard/base-types/best-practices-strings.md) article for an example that demonstrates how culture-sensitive string operations can produce inconsistent results.</span></span>  
  
## <a name="using-the-stringtoupper-and-stringtolower-methods"></a><span data-ttu-id="f4b5e-113">Uso dei metodi String.ToUpper e String.ToLower</span><span class="sxs-lookup"><span data-stu-id="f4b5e-113">Using the String.ToUpper and String.ToLower Methods</span></span>  
 <span data-ttu-id="f4b5e-114">Per ottenere una maggiore chiarezza del codice, è consigliabile usare sempre gli overload dei metodi `String.ToUpper` e `String.ToLower`, che consentono di specificare un parametro `culture` in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="f4b5e-114">For code clarity, it is recommended that you always use overloads of the `String.ToUpper` and `String.ToLower` methods that allow you to specify a `culture` parameter explicitly.</span></span> <span data-ttu-id="f4b5e-115">Nel codice seguente, ad esempio, viene eseguita una ricerca dell'identificatore.</span><span class="sxs-lookup"><span data-stu-id="f4b5e-115">For example, the following code performs an identifier lookup.</span></span> <span data-ttu-id="f4b5e-116">L'operazione `key.ToLower` non dipende dalle impostazioni cultura per impostazione predefinita, ma questo comportamento non è evidente da una lettura del codice.</span><span class="sxs-lookup"><span data-stu-id="f4b5e-116">The `key.ToLower` operation is culture-sensitive by default, but this behavior is not clear from reading the code.</span></span>  
  
### <a name="example"></a><span data-ttu-id="f4b5e-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="f4b5e-117">Example</span></span>  
  
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
  
 <span data-ttu-id="f4b5e-118">Se si desidera che l'operazione `key.ToLower` non dipenda dalle impostazioni cultura, è necessario modificare l'esempio precedente come indicato di seguito per usare in modo esplicito `CultureInfo.InvariantCulture` in caso di modifica di maiuscole/minuscole.</span><span class="sxs-lookup"><span data-stu-id="f4b5e-118">If you want the `key.ToLower` operation to be culture-insensitive, you should change the preceding example as follows to explicitly use the `CultureInfo.InvariantCulture` when changing the case.</span></span>  
  
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
  
## <a name="using-the-chartoupper-and-chartolower-methods"></a><span data-ttu-id="f4b5e-119">Uso dei metodi Char.ToUpper e Char.ToLower</span><span class="sxs-lookup"><span data-stu-id="f4b5e-119">Using the Char.ToUpper and Char.ToLower Methods</span></span>  
 <span data-ttu-id="f4b5e-120">Sebbene i metodi `Char.ToUpper` e `Char.ToLower` abbiano le stesse caratteristiche dei metodi `String.ToUpper` e `String.ToLower`, le uniche impostazioni cultura su cui hanno effetto sono Turco (Turchia) e Azerbaigiano (alfabeto latino, Azerbaigian).</span><span class="sxs-lookup"><span data-stu-id="f4b5e-120">Although the `Char.ToUpper` and `Char.ToLower` methods have the same characteristics as the `String.ToUpper` and `String.ToLower` methods, the only cultures that are affected are Turkish (Turkey) and Azerbaijani (Latin, Azerbaijan).</span></span> <span data-ttu-id="f4b5e-121">Queste sono le uniche due impostazioni cultura con differenze di maiuscole e minuscole a carattere singolo.</span><span class="sxs-lookup"><span data-stu-id="f4b5e-121">These are the only two cultures with single-character casing differences.</span></span> <span data-ttu-id="f4b5e-122">Per informazioni dettagliate su questo mapping di maiuscole e minuscole univoco, vedere la sezione "Maiuscole e minuscole" dell'argomento della classe <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="f4b5e-122">For more details about this unique case mapping, see the "Casing" section in the <xref:System.String> class topic.</span></span> <span data-ttu-id="f4b5e-123">Per maggiore chiarezza del codice e per garantire risultati coerenti, è consigliabile usare sempre gli overload di questi metodi che consentono di specificare in modo esplicito un parametro `culture`.</span><span class="sxs-lookup"><span data-stu-id="f4b5e-123">For code clarity and to ensure consistent results, it is recommended that you always use the overloads of these methods that allow you to explicitly specify a `culture` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4b5e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4b5e-124">See also</span></span>

- <xref:System.String.ToUpper%2A?displayProperty=nameWithType>
- <xref:System.String.ToLower%2A?displayProperty=nameWithType>
- <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>
- <xref:System.Char.ToLower%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f4b5e-125">Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura</span><span class="sxs-lookup"><span data-stu-id="f4b5e-125">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
