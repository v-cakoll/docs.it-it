---
title: Procedure consigliate per l&quot;uso delle stringhe
description: Procedure consigliate per l&quot;uso delle stringhe
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: b3cefaa4-0a3f-4a96-aba9-1de30fb07c29
ms.translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 3efd30bade564fe1b7dbf93237a9ff40c58c5f1e
ms.contentlocale: it-it
ms.lasthandoff: 11/05/2016

---

# <a name="best-practices-for-using-strings"></a><span data-ttu-id="99b3a-104">Procedure consigliate per l'uso delle stringhe</span><span class="sxs-lookup"><span data-stu-id="99b3a-104">Best practices for using strings</span></span>

<span data-ttu-id="99b3a-105">.NET offre un ampio supporto per lo sviluppo di applicazioni localizzate e globalizzate e semplifica l'applicazione delle convenzioni relative alle impostazioni cultura correnti o alle impostazioni cultura specifiche quando si eseguono operazioni comuni come l'ordinamento e la visualizzazione delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="99b3a-105">.NET provides extensive support for developing localized and globalized applications, and makes it easy to apply the conventions of either the current culture or a specific culture when performing common operations such as sorting and displaying strings.</span></span> <span data-ttu-id="99b3a-106">Tuttavia, l'ordinamento o il confronto delle stringhe non è sempre un'operazione con distinzione delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="99b3a-106">But sorting or comparing strings is not always a culture-sensitive operation.</span></span> <span data-ttu-id="99b3a-107">Ad esempio, le stringhe usate internamente da un'applicazione in genere devono essere gestite in modo identico in tutte le impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="99b3a-107">For example, strings that are used internally by an application typically should be handled identically across all cultures.</span></span> <span data-ttu-id="99b3a-108">Quando i dati di stringa indipendenti dalle impostazioni cultura, ad esempio i tag XML, i tag HTML, i nomi utente, i percorsi di file e i nomi degli oggetti di sistema, vengono interpretati come dati con distinzione delle impostazioni cultura, nel codice dell'applicazione possono verificarsi bug complessi, riduzioni delle prestazioni e, in alcuni casi, problemi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="99b3a-108">When culturally independent string data, such as XML tags, HTML tags, user names, file paths, and the names of system objects, are interpreted as if they were culture-sensitive, application code can be subject to subtle bugs, poor performance, and, in some cases, security issues.</span></span>

<span data-ttu-id="99b3a-109">Questo articolo esamina i metodi di ordinamento, confronto e utilizzo di maiuscole e minuscole nelle stringhe in .NET, offre delle raccomandazioni per selezionare il metodo di gestione delle stringhe appropriato e fornisce informazioni aggiuntive sui metodi di gestione delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="99b3a-109">This article examines the string sorting, comparison, and casing methods in .NET, presents recommendations for selecting an appropriate string-handling method, and provides additional information about string-handling methods.</span></span> <span data-ttu-id="99b3a-110">Inoltre, esamina come vengono gestiti i file formattati, ad esempio i dati numerici e i dati relativi a data e ora, per la visualizzazione e l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="99b3a-110">It also examines how formatted data, such as numeric data and date and time data, is handled for display and for storage.</span></span> 

<span data-ttu-id="99b3a-111">In questo articolo sono contenute le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="99b3a-111">This article contains the following sections:</span></span>

* [<span data-ttu-id="99b3a-112">Suggerimenti per l'uso delle stringhe</span><span class="sxs-lookup"><span data-stu-id="99b3a-112">Recommendations for string usage</span></span>](#recommendations-for-string-usage)

* [<span data-ttu-id="99b3a-113">Specifica esplicita per il confronto tra stringhe</span><span class="sxs-lookup"><span data-stu-id="99b3a-113">Specifying string comparisons explicitly</span></span>](#specifying-string-comparisons-explicitly)

* [<span data-ttu-id="99b3a-114">Dettagli sul confronto tra stringhe</span><span class="sxs-lookup"><span data-stu-id="99b3a-114">The details of string comparison</span></span>](#the-details-of-string-comparison)

* [<span data-ttu-id="99b3a-115">Scelta di un membro StringComparison per la chiamata al metodo</span><span class="sxs-lookup"><span data-stu-id="99b3a-115">Choosing a StringComparison member for your method call</span></span>](#choosing-a-stringcomparison-member-for-your-method-call)

* [<span data-ttu-id="99b3a-116">Metodi comuni per il confronto tra stringhe</span><span class="sxs-lookup"><span data-stu-id="99b3a-116">Common string comparison methods</span></span>](#common-string-comparison-methods)

* [<span data-ttu-id="99b3a-117">Metodi che eseguono indirettamente il confronto tra stringhe</span><span class="sxs-lookup"><span data-stu-id="99b3a-117">Methods that perform string comparison indirectly</span></span>](#methods-that-perform-string-comparison-indirectly)

* [<span data-ttu-id="99b3a-118">Visualizzazione e conservazione dei dati formattati</span><span class="sxs-lookup"><span data-stu-id="99b3a-118">Displaying and persisting formatted data</span></span>](#displaying-and-persisting-formatted-data)

## <a name="recommendations-for-string-usage"></a><span data-ttu-id="99b3a-119">Suggerimenti per l'uso delle stringhe</span><span class="sxs-lookup"><span data-stu-id="99b3a-119">Recommendations for string usage</span></span>

<span data-ttu-id="99b3a-120">Quando si sviluppa con .NET, seguire queste semplici raccomandazione quando si usano le stringhe:</span><span class="sxs-lookup"><span data-stu-id="99b3a-120">When you develop with .NET, follow these simple recommendations when you use strings:</span></span> 

* <span data-ttu-id="99b3a-121">Usare gli overload che specificano esplicitamente le regole di confronto tra stringhe per le operazioni di stringa.</span><span class="sxs-lookup"><span data-stu-id="99b3a-121">Use overloads that explicitly specify the string comparison rules for string operations.</span></span> <span data-ttu-id="99b3a-122">In genere, questo implica chiamare un overload del metodo con un parametro di tipo [StringComparison](xref:System.StringComparison).</span><span class="sxs-lookup"><span data-stu-id="99b3a-122">Typically, this involves calling a method overload that has a parameter of type [StringComparison](xref:System.StringComparison).</span></span>

* <span data-ttu-id="99b3a-123">Usare [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) o [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) per i confronti come valore predefinito sicuro per una corrispondenza tra stringhe indipendente dalla cultura.</span><span class="sxs-lookup"><span data-stu-id="99b3a-123">Use [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) for comparisons as your safe default for culture-agnostic string matching.</span></span>

* <span data-ttu-id="99b3a-124">Usare i confronti con [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) o [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) per ottenere prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="99b3a-124">Use comparisons with [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) for better performance.</span></span>

* <span data-ttu-id="99b3a-125">Usare operazioni di stringa basate su [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) quando si visualizza l'output all'utente.</span><span class="sxs-lookup"><span data-stu-id="99b3a-125">Use string operations that are based on [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) when you display output to the user.</span></span>

* <span data-ttu-id="99b3a-126">Usare i valori non linguistici [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) o [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) anziché le operazioni di stringa basate su [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) quando il confronto non è rilevante linguisticamente, ad esempio è simbolico.</span><span class="sxs-lookup"><span data-stu-id="99b3a-126">Use the non-linguistic [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) values instead of string operations based on [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) when the comparison is linguistically irrelevant (symbolic, for example).</span></span>

* <span data-ttu-id="99b3a-127">Usare il metodo [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) anziché il metodo [String.ToLowerInvariant](xref:System.String.ToLowerInvariant) quando si normalizzano le stringhe per il confronto.</span><span class="sxs-lookup"><span data-stu-id="99b3a-127">Use the [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) method instead of the [String.ToLowerInvariant](xref:System.String.ToLowerInvariant) method when you normalize strings for comparison.</span></span>

* <span data-ttu-id="99b3a-128">Usare un overload del metodo [String](xref:System.String) `Equals` per controllare se due stringhe sono uguali.</span><span class="sxs-lookup"><span data-stu-id="99b3a-128">Use an overload of the [String](xref:System.String) `Equals` method to test whether two strings are equal.</span></span>

* <span data-ttu-id="99b3a-129">Usare un overload dei metodi [String](xref:System.String) `Compare` e [String.CompareTo](xref:System.String.CompareTo(System.String)) per ordinare le stringhe senza controllare se sono uguali.</span><span class="sxs-lookup"><span data-stu-id="99b3a-129">Use an overload of the [String](xref:System.String) `Compare` and [String.CompareTo](xref:System.String.CompareTo(System.String)) methods to sort strings, not to check for equality.</span></span>

* <span data-ttu-id="99b3a-130">Usare la formattazione con distinzione delle impostazioni cultura per visualizzare i dati non di tipo stringa, ad esempio numeri e dati, in un'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="99b3a-130">Use culture-sensitive formatting to display non-string data, such as numbers and dates, in a user interface.</span></span> <span data-ttu-id="99b3a-131">Usare la formattazione con la lingua inglese per conservare i dati non di tipo stringa in formato stringa.</span><span class="sxs-lookup"><span data-stu-id="99b3a-131">Use formatting with the invariant culture to persist non-string data in string form.</span></span>

<span data-ttu-id="99b3a-132">Evitare le operazioni seguenti quando si usano le stringhe:</span><span class="sxs-lookup"><span data-stu-id="99b3a-132">Avoid the following practices when you use strings:</span></span>

* <span data-ttu-id="99b3a-133">Non usare overload che non specificano in modo esplicito o implicito le regole di confronto tra stringhe per le operazioni di stringa.</span><span class="sxs-lookup"><span data-stu-id="99b3a-133">Do not use overloads that do not explicitly or implicitly specify the string comparison rules for string operations.</span></span> 

* <span data-ttu-id="99b3a-134">Non usare un overload del metodo [String](xref:System.String) `Compare` o [String.CompareTo](xref:System.String.CompareTo(System.String)) ed eseguire un test per il valore restituito zero per determinare se due stringhe sono uguali.</span><span class="sxs-lookup"><span data-stu-id="99b3a-134">Do not use an overload of the [String](xref:System.String) `Compare` or [String.CompareTo](xref:System.String.CompareTo(System.String)) methods and test for a return value of zero to determine whether two strings are equal.</span></span>

* <span data-ttu-id="99b3a-135">Non usare la formattazione con distinzione delle impostazioni cultura per conservare i dati numerici o di data e ora in formato stringa.</span><span class="sxs-lookup"><span data-stu-id="99b3a-135">Do not use culture-sensitive formatting to persist numeric data or date and time data in string form.</span></span>

## <a name="specifying-string-comparisons-explicitly"></a><span data-ttu-id="99b3a-136">Specifica esplicita per il confronto tra stringhe</span><span class="sxs-lookup"><span data-stu-id="99b3a-136">Specifying string comparisons explicitly</span></span>

<span data-ttu-id="99b3a-137">Molti dei metodi di modifica delle stringhe in .NET sono di tipo overload.</span><span class="sxs-lookup"><span data-stu-id="99b3a-137">Most of the string manipulation methods in .NET are overloaded.</span></span> <span data-ttu-id="99b3a-138">In genere, uno o più overload accettano le impostazioni predefinite, mentre altri accettano le impostazioni non predefinite, specificando invece una determinata procedura di confronto o modifica delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="99b3a-138">Typically, one or more overloads accept default settings, whereas others accept no defaults and instead define the precise way in which strings are to be compared or manipulated.</span></span> <span data-ttu-id="99b3a-139">La maggior parte dei metodi che non si basano sulle impostazioni predefinite include un parametro di tipo [StringComparison](xref:System.StringComparison), che corrisponde a un'enumerazione che specifica in modo esplicito le regole per il confronto tra stringhe in base alle impostazioni cultura e alle maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="99b3a-139">Most of the methods that do not rely on defaults include a parameter of type [StringComparison](xref:System.StringComparison), which is an enumeration that explicitly specifies rules for string comparison by culture and case.</span></span> <span data-ttu-id="99b3a-140">La tabella seguente descrive i membri dell'enumerazione [StringComparison](xref:System.StringComparison).</span><span class="sxs-lookup"><span data-stu-id="99b3a-140">The following table describes the [StringComparison](xref:System.StringComparison) enumeration members.</span></span> 

<span data-ttu-id="99b3a-141">Membro StringComparison</span><span class="sxs-lookup"><span data-stu-id="99b3a-141">StringComparison member</span></span> | <span data-ttu-id="99b3a-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99b3a-142">Description</span></span>
----------------------- | -----------
[<span data-ttu-id="99b3a-143">StringComparison.CurrentCulture</span><span class="sxs-lookup"><span data-stu-id="99b3a-143">StringComparison.CurrentCulture</span></span>](xref:System.StringComparison.CurrentCulture) | <span data-ttu-id="99b3a-144">Esegue un confronto con distinzione tra maiuscole e minuscole usando le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="99b3a-144">Performs a case-sensitive comparison using the current culture.</span></span>
[<span data-ttu-id="99b3a-145">CurrentCultureIgnoreCase</span><span class="sxs-lookup"><span data-stu-id="99b3a-145">CurrentCultureIgnoreCase</span></span>](xref:System.StringComparison.CurrentCultureIgnoreCase) | <span data-ttu-id="99b3a-146">Esegue un confronto senza distinzione tra maiuscole e minuscole usando le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="99b3a-146">Performs a case-insensitive comparison using the current culture.</span></span>
[<span data-ttu-id="99b3a-147">StringComparison.Ordinal</span><span class="sxs-lookup"><span data-stu-id="99b3a-147">StringComparison.Ordinal</span></span>](xref:System.StringComparison.Ordinal) | <span data-ttu-id="99b3a-148">Esegue un confronto ordinale.</span><span class="sxs-lookup"><span data-stu-id="99b3a-148">Performs an ordinal comparison.</span></span>
[<span data-ttu-id="99b3a-149">StringComparison.OrdinalIgnoreCase</span><span class="sxs-lookup"><span data-stu-id="99b3a-149">StringComparison.OrdinalIgnoreCase</span></span>](xref:System.StringComparison.OrdinalIgnoreCase) | <span data-ttu-id="99b3a-150">Esegue un confronto ordinale senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="99b3a-150">Performs a case-insensitive ordinal comparison.</span></span>

<span data-ttu-id="99b3a-151">Ad esempio, il metodo [String](xref:System.String) `IndexOf`, che restituisce l'indice di una sottostringa in un oggetto [String](xref:System.String) che corrisponde a un carattere o a una stringa, ha nove overload:</span><span class="sxs-lookup"><span data-stu-id="99b3a-151">For example, the [String](xref:System.String) `IndexOf` method, which returns the index of a substring in a [String](xref:System.String) object that matches either a character or a string, has nine overloads:</span></span>

* <span data-ttu-id="99b3a-152">[IndexOf(Char)](xref:System.String.IndexOf(System.Char)), [IndexOf(Char, Int32)](xref:System.String.IndexOf(System.Char,System.Int32)) e [IndexOf(Char, Int32, Int32)](xref:System.String.IndexOf(System.Char,System.Int32,System.Int32)), che per impostazione predefinita eseguono una ricerca ordinale (con distinzione tra maiuscole e minuscole e senza distinzione delle impostazioni cultura) per un carattere nella stringa.</span><span class="sxs-lookup"><span data-stu-id="99b3a-152">[IndexOf(Char)](xref:System.String.IndexOf(System.Char)), [IndexOf(Char, Int32)](xref:System.String.IndexOf(System.Char,System.Int32)), and [IndexOf(Char, Int32, Int32)](xref:System.String.IndexOf(System.Char,System.Int32,System.Int32)), which by default perform an ordinal (case-sensitive and culture-insensitive) search for a character in the string.</span></span>

* <span data-ttu-id="99b3a-153">[IndexOf(String)](xref:System.String.IndexOf(System.String)), [IndexOf(String, Int32)](xref:System.String.IndexOf(System.String,System.Int32)) e [IndexOf(String, Int32, Int32)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32)), che per impostazione predefinita eseguono una ricerca con distinzione tra maiuscole e minuscole e con distinzione delle impostazioni cultura per una sottostringa nella stringa.</span><span class="sxs-lookup"><span data-stu-id="99b3a-153">[IndexOf(String)](xref:System.String.IndexOf(System.String)), [IndexOf(String, Int32)](xref:System.String.IndexOf(System.String,System.Int32)), and [IndexOf(String, Int32, Int32)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32)), which by default perform a case-sensitive and culture-sensitive search for a substring in the string.</span></span>

* <span data-ttu-id="99b3a-154">[IndexOf(String, StringComparison)](xref:System.String.IndexOf(System.String,System.StringComparison)), [IndexOf(String, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.StringComparison)) e [IndexOf(String, Int32, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32,System.StringComparison)), che includono un parametro di tipo StringComparison che consente di specificare il tipo di confronto.</span><span class="sxs-lookup"><span data-stu-id="99b3a-154">[IndexOf(String, StringComparison)](xref:System.String.IndexOf(System.String,System.StringComparison)), [IndexOf(String, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.StringComparison)), and [IndexOf(String, Int32, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32,System.StringComparison)), which include a parameter of type StringComparison that allows the form of the comparison to be specified.</span></span>

<span data-ttu-id="99b3a-155">Si consiglia di selezione un overload che non uso i valori predefiniti, per i seguenti motivi:</span><span class="sxs-lookup"><span data-stu-id="99b3a-155">We recommend that you select an overload that does not use default values, for the following reasons:</span></span>

* <span data-ttu-id="99b3a-156">Alcuni overload con parametri predefiniti (quelli che cercano [Char](xref:System.Char) nell'istanza della stringa) eseguono un confronto ordinale, mentre altri (quelli che cercano una stringa nell'istanza della stringa) applicano la distinzione delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="99b3a-156">Some overloads with default parameters (those that search for a [Char](xref:System.Char) in the string instance) perform an ordinal comparison, whereas others (those that search for a string in the string instance) are culture-sensitive.</span></span> <span data-ttu-id="99b3a-157">È difficile ricordare quale valore predefinito viene usato dai diversi metodi ed è facile confondere gli overload.</span><span class="sxs-lookup"><span data-stu-id="99b3a-157">It is difficult to remember which method uses which default value, and easy to confuse the overloads.</span></span>

* <span data-ttu-id="99b3a-158">Lo scopo del codice basato sui valori predefiniti per le chiamate al metodo non è chiaro.</span><span class="sxs-lookup"><span data-stu-id="99b3a-158">The intent of the code that relies on default values for method calls is not clear.</span></span> <span data-ttu-id="99b3a-159">Nell'esempio seguente, che si basa su impostazioni predefinite, è difficile capire se lo sviluppatore intendeva eseguire un confronto ordinale o linguistico tra due stringhe o se la differenza tra maiuscole e minuscole tra `protocol` e "http" può causare la restituzione di `false` nel test di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="99b3a-159">In the following example, which relies on defaults, it is difficult to know whether the developer actually intended an ordinal or a linguistic comparison of two strings, or whether a case difference between `protocol` and "http" might cause the test for equality to return `false`.</span></span>

  ```csharp
  string protocol = GetProtocol(url);       
  if (String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase)) {
     // ...Code to handle HTTP protocol.
  }
  else {
     throw new InvalidOperationException();
  }
  ```

  ```vb
  Dim protocol As String = GetProtocol(url)       
  If String.Equals(protocol, "http") Then
    ' ...Code to handle HTTP protocol.
  Else
     Throw New InvalidOperationException()
  End If
  ```

<span data-ttu-id="99b3a-160">In generale, si consiglia di chiamare un metodo non basato sulle impostazioni predefinite perché disambigua lo scopo del codice.</span><span class="sxs-lookup"><span data-stu-id="99b3a-160">In general, we recommend that you call a method that does not rely on defaults, because it makes the intent of the code unambiguous.</span></span> <span data-ttu-id="99b3a-161">In questo modo, anche il codice diventa più leggibile ed è più facile eseguirne il debug e la manutenzione.</span><span class="sxs-lookup"><span data-stu-id="99b3a-161">This, in turn, makes the code more readable and easier to debug and maintain.</span></span> <span data-ttu-id="99b3a-162">L'esempio seguente riguarda le domande relative all'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="99b3a-162">The following example addresses the questions raised about the previous example.</span></span> <span data-ttu-id="99b3a-163">Viene specificato che viene utilizzato il confronto ordinale e che le differenze tra maiuscole e minuscole vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="99b3a-163">It makes it clear that ordinal comparison is used and that differences in case are ignored.</span></span> 

```csharp
string protocol = GetProtocol(url);       
if (String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase)) {
   // ...Code to handle HTTP protocol.
}
else {
   throw new InvalidOperationException();
}
```

```vb
Dim protocol As String = GetProtocol(url)       
If String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase) Then
   ' ...Code to handle HTTP protocol.
Else
   Throw New InvalidOperationException()
End If
```

## <a name="the-details-of-string-comparison"></a><span data-ttu-id="99b3a-164">Dettagli sul confronto tra stringhe</span><span class="sxs-lookup"><span data-stu-id="99b3a-164">The details of string comparison</span></span>

<span data-ttu-id="99b3a-165">Il confronto tra stringhe è la base di molte operazioni relative alle stringhe, in particolare l'ordinamento e il test di uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="99b3a-165">String comparison is the heart of many string-related operations, particularly sorting and testing for equality.</span></span> <span data-ttu-id="99b3a-166">L'ordinamento delle stringhe viene eseguito in un modo specifico: se "my" compare prima di "string" in un elenco ordinato di stringhe, nel confronto "my" deve essere minore o uguale a "string".</span><span class="sxs-lookup"><span data-stu-id="99b3a-166">Strings sort in a determined order: If "my" appears before "string" in a sorted list of strings, "my" must compare less than or equal to "string".</span></span> <span data-ttu-id="99b3a-167">Inoltre, il confronto definisce implicitamente l'uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="99b3a-167">Additionally, comparison implicitly defines equality.</span></span> <span data-ttu-id="99b3a-168">L'operazione di confronto restituisce zero per le stringhe che considera uguali.</span><span class="sxs-lookup"><span data-stu-id="99b3a-168">The comparison operation returns zero for strings it deems equal.</span></span> <span data-ttu-id="99b3a-169">In altre parole, nessuna stringa viene considerata minore delle altre.</span><span class="sxs-lookup"><span data-stu-id="99b3a-169">A good interpretation is that neither string is less than the other.</span></span> <span data-ttu-id="99b3a-170">Le operazioni più significative relative alle stringhe includono una o più delle seguenti procedure: confronto con un'altra stringa ed esecuzione di un'operazione di ordinamento definita correttamente.</span><span class="sxs-lookup"><span data-stu-id="99b3a-170">Most meaningful operations involving strings include one or both of these procedures: comparing with another string, and executing a well-defined sort operation.</span></span>

<span data-ttu-id="99b3a-171">Tuttavia, la valutazione di due stringhe per l'uguaglianza e l'ordinamento non produce un unico risultato corretto; l'esito dipende dai criteri usati per il confronto delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="99b3a-171">However, evaluating two strings for equality or sort order does not yield a single, correct result; the outcome depends on the criteria used to compare the strings.</span></span> <span data-ttu-id="99b3a-172">In particolare, i confronti tra stringhe ordinali o basati sulle convenzioni di utilizzo di maiuscole e minuscole e di ordinamento delle impostazioni cultura correnti o della lingua inglese (impostazioni indipendenti dalle impostazioni cultura basate sulla lingua inglese) possono produrre risultati diversi.</span><span class="sxs-lookup"><span data-stu-id="99b3a-172">In particular, string comparisons that are ordinal or that are based on the casing and sorting conventions of the current culture or the invariant culture (a locale-agnostic culture based on the English language) may produce different results.</span></span>

### <a name="string-comparisons-that-use-the-current-culture"></a><span data-ttu-id="99b3a-173">Confronti tra stringhe che usano le impostazioni cultura correnti</span><span class="sxs-lookup"><span data-stu-id="99b3a-173">String comparisons that use the current culture</span></span>

<span data-ttu-id="99b3a-174">Un criterio prevede l'uso delle convenzioni delle impostazioni cultura correnti quando si confrontano le stringhe.</span><span class="sxs-lookup"><span data-stu-id="99b3a-174">One criterion involves using the conventions of the current culture when comparing strings.</span></span> <span data-ttu-id="99b3a-175">I confronti basati sulle impostazioni cultura correnti usano le impostazioni cultura o le impostazioni locali correnti del thread.</span><span class="sxs-lookup"><span data-stu-id="99b3a-175">Comparisons that are based on the current culture use the thread's current culture or locale.</span></span> <span data-ttu-id="99b3a-176">È necessario usare sempre i confronti basati sulle impostazioni cultura correnti quando i dati sono linguisticamente rilevanti e quando riflettono un'interazione utente con distinzione delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="99b3a-176">You should always use comparisons that are based on the current culture when data is linguistically relevant, and when it reflects culture-sensitive user interaction.</span></span> 

<span data-ttu-id="99b3a-177">Tuttavia, il comportamento di confronto e di utilizzo di maiuscole e minuscole in .NET cambia quando vengono modificate le impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="99b3a-177">However, comparison and casing behavior in .NET changes when the culture changes.</span></span> <span data-ttu-id="99b3a-178">Ciò accade quando un'applicazione viene eseguita in un computer con impostazioni cultura diverse da quelle del computer in cui è stata sviluppata oppure quando il thread di esecuzione modifica le proprie impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="99b3a-178">This happens when an application executes on a computer that has a different culture than the computer on which the application was developed, or when the executing thread changes its culture.</span></span> <span data-ttu-id="99b3a-179">Questo comportamento è intenzionale, tuttavia resta poco chiaro per molti sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="99b3a-179">This behavior is intentional, but it remains non-obvious to many developers.</span></span> <span data-ttu-id="99b3a-180">L'esempio seguente illustra le differenze nell'ordinamento tra le impostazioni cultura della lingua inglese per gli Stati Uniti ("en-US") e di quella svedese ("sv-SE").</span><span class="sxs-lookup"><span data-stu-id="99b3a-180">The following example illustrates differences in sort order between the U.S. English ("en-US") and Swedish ("sv-SE") cultures.</span></span> <span data-ttu-id="99b3a-181">Si noti che le parole "ångström", "Windows" e "Visual Studio" vengono visualizzate in posizioni diverse nelle matrici di stringhe ordinate.</span><span class="sxs-lookup"><span data-stu-id="99b3a-181">Note that the words "ångström", "Windows", and "Visual Studio" appear in different positions in the sorted string arrays.</span></span>

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] values= { "able", "ångström", "apple", "Æble", 
                         "Windows", "Visual Studio" };
      Array.Sort(values);
      DisplayArray(values);

      // Change culture to Swedish (Sweden).
      string originalCulture = CultureInfo.CurrentCulture.Name;
      Thread.CurrentThread.CurrentCulture = new CultureInfo("sv-SE");
      Array.Sort(values);
      DisplayArray(values);

      // Restore the original culture.
      Thread.CurrentThread.CurrentCulture = new CultureInfo(originalCulture);
    }

    private static void DisplayArray(string[] values)
    {
      Console.WriteLine("Sorting using the {0} culture:",  
                        CultureInfo.CurrentCulture.Name);
      foreach (string value in values)
         Console.WriteLine("   {0}", value);

      Console.WriteLine();
    }
}
// The example displays the following output:
//       Sorting using the en-US culture:
//          able
//          Æble
//          ångström
//          apple
//          Visual Studio
//          Windows
//       
//       Sorting using the sv-SE culture:
//          able
//          Æble
//          apple
//          Windows
//          Visual Studio
//          ångström
```

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim values() As String = { "able", "ångström", "apple", _
                                 "Æble", "Windows", "Visual Studio" }
      Array.Sort(values)
      DisplayArray(values)

      ' Change culture to Swedish (Sweden).
      Dim originalCulture As String = CultureInfo.CurrentCulture.Name
      Thread.CurrentThread.CurrentCulture = New CultureInfo("sv-SE")
      Array.Sort(values)
      DisplayArray(values)

      ' Restore the original culture.
      Thread.CurrentThread.CurrentCulture = New CultureInfo(originalCulture)
    End Sub

    Private Sub DisplayArray(values() As String)
      Console.WRiteLine("Sorting using the {0} culture:", _ 
                        CultureInfo.CurrentCulture.Name)
      For Each value As String In values
         Console.WriteLine("   {0}", value)
      Next
      Console.WriteLine()   
    End Sub
End Module
' The example displays the following output:
'       Sorting using the en-US culture:
'          able
'          Æble
'          ångström
'          apple
'          Visual Studio
'          Windows
'       
'       Sorting using the sv-SE culture:
'          able
'          Æble
'          apple
'          Windows
'          Visual Studio
'          ångström
```

<span data-ttu-id="99b3a-182">I confronti senza distinzione tra maiuscole e minuscole che usano le impostazioni cultura correnti sono uguali a quelli con distinzione delle impostazioni cultura, ma ignorano la distinzione tra maiuscole e minuscole come indicato dalle impostazioni cultura correnti del thread.</span><span class="sxs-lookup"><span data-stu-id="99b3a-182">Case-insensitive comparisons that use the current culture are the same as culture-sensitive comparisons, except that they ignore case as dictated by the thread's current culture.</span></span> <span data-ttu-id="99b3a-183">Questo comportamento può manifestarsi anche negli ordinamenti.</span><span class="sxs-lookup"><span data-stu-id="99b3a-183">This behavior may manifest itself in sort orders as well.</span></span> 

<span data-ttu-id="99b3a-184">I confronti che usano la semantica delle impostazioni cultura correnti sono i confronti predefiniti per i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="99b3a-184">Comparisons that use current culture semantics are the default for the following methods:</span></span>

* <span data-ttu-id="99b3a-185">Overload di [String](xref:System.String) `Compare` che non includono un parametro [StringComparison](xref:System.StringComparison).</span><span class="sxs-lookup"><span data-stu-id="99b3a-185">[String](xref:System.String) `Compare` overloads that do not include a [StringComparison](xref:System.StringComparison) parameter.</span></span>

* <span data-ttu-id="99b3a-186">Overload di [String.CompareTo](xref:System.String.CompareTo(System.String)).</span><span class="sxs-lookup"><span data-stu-id="99b3a-186">[String.CompareTo](xref:System.String.CompareTo(System.String)) overloads.</span></span>

* <span data-ttu-id="99b3a-187">Metodo [String.StartsWith(String)](xref:System.String.StartsWith(System.String)) predefinito.</span><span class="sxs-lookup"><span data-stu-id="99b3a-187">The default [String.StartsWith(String)](xref:System.String.StartsWith(System.String)) method.</span></span> 

* <span data-ttu-id="99b3a-188">Metodo [String.EndsWith(String)](xref:System.String.EndsWith(System.String)) predefinito.</span><span class="sxs-lookup"><span data-stu-id="99b3a-188">The default [String.EndsWith(String)](xref:System.String.EndsWith(System.String)) method.</span></span>

* <span data-ttu-id="99b3a-189">Overload di [String](xref:System.String) `IndexOf` che accettano [String](xref:System.String) come parametro di ricerca e non includono un parametro [StringComparison](xref:System.StringComparison).</span><span class="sxs-lookup"><span data-stu-id="99b3a-189">[String](xref:System.String) `IndexOf` overloads that accept a [String](xref:System.String) as a search parameter and that do not have a [StringComparison](xref:System.StringComparison) parameter.</span></span>

* <span data-ttu-id="99b3a-190">Overload di [String](xref:System.String) `LastIndexOf` che accettano [String](xref:System.String) come parametro di ricerca e non includono un parametro [StringComparison](xref:System.StringComparison).</span><span class="sxs-lookup"><span data-stu-id="99b3a-190">[String](xref:System.String) `LastIndexOf` overloads that accept a [String](xref:System.String) as a search parameter and that do not have a [StringComparison](xref:System.StringComparison) parameter.</span></span>

<span data-ttu-id="99b3a-191">In ogni caso, si consiglia di chiamare un overload con il parametro [StringComparison](xref:System.StringComparison) per rendere chiaro lo scopo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="99b3a-191">In any case, we recommend that you call an overload that has a [StringComparison](xref:System.StringComparison) parameter to make the intent of the method call clear.</span></span> 

<span data-ttu-id="99b3a-192">È possibile che vengano generati bug complessi e meno complessi quando i dati non linguistici della stringa vengono interpretati linguisticamente oppure quando i dati della stringa di specifiche impostazioni cultura vengono interpretati usando le convenzioni di altre impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="99b3a-192">Subtle and not so subtle bugs can emerge when non-linguistic string data is interpreted linguistically, or when string data from a particular culture is interpreted using the conventions of another culture.</span></span> <span data-ttu-id="99b3a-193">L'esempio canonico è il problema della I turca.</span><span class="sxs-lookup"><span data-stu-id="99b3a-193">The canonical example is the Turkish-I problem.</span></span>

<span data-ttu-id="99b3a-194">Per quasi tutti gli alfabeti latini, incluso l'inglese (Stati Uniti), il carattere "i" (\u0069) corrisponde alla versione minuscola del carattere "I" (\u0049).</span><span class="sxs-lookup"><span data-stu-id="99b3a-194">For nearly all Latin alphabets, including U.S. English, the character "i" (\u0069) is the lowercase version of the character "I" (\u0049).</span></span> <span data-ttu-id="99b3a-195">Questa regola di utilizzo di maiuscole e minuscole diventa rapidamente l'impostazione predefinita per chi programma queste impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="99b3a-195">This casing rule quickly becomes the default for someone programming in such a culture.</span></span> <span data-ttu-id="99b3a-196">Tuttavia, l'alfabeto turco ("tr-TR") include una "I con punto", "İ" (\u0130), che è la versione maiuscola di "i".</span><span class="sxs-lookup"><span data-stu-id="99b3a-196">However, the Turkish ("tr-TR") alphabet includes an "I with a dot" character "İ" (\u0130), which is the capital version of "i".</span></span> <span data-ttu-id="99b3a-197">L'alfabeto turco include anche una "i senza punto" minuscola, "ı" (\u0131), la cui versione maiuscola è "I".</span><span class="sxs-lookup"><span data-stu-id="99b3a-197">Turkish also includes a lowercase "i without a dot" character, "ı" (\u0131), which capitalizes to "I".</span></span> <span data-ttu-id="99b3a-198">Questo comportamento si verifica anche con le impostazioni cultura azera ("az").</span><span class="sxs-lookup"><span data-stu-id="99b3a-198">This behavior occurs in the Azerbaijani ("az") culture as well.</span></span>

<span data-ttu-id="99b3a-199">Pertanto, i presupposti relativi all'uso della maiuscola per "i" o della minuscola per "I" non sono validi in tutte le impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="99b3a-199">Therefore, assumptions made about capitalizing "i" or lowercasing "I" are not valid among all cultures.</span></span> <span data-ttu-id="99b3a-200">Se si usano gli overload predefiniti per le routine di confronto tra stringhe, questi saranno soggetti a variazioni tra le diverse impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="99b3a-200">If you use the default overloads for string comparison routines, they will be subject to variance between cultures.</span></span> <span data-ttu-id="99b3a-201">Se i dati da confrontare sono di tipo non linguistico, l'uso degli overload predefiniti può produrre risultati indesiderati, come illustrato in questo tentativo di eseguire un confronto senza distinzione tra maiuscole e minuscole delle stringhe "file" e "FILE".</span><span class="sxs-lookup"><span data-stu-id="99b3a-201">If the data to be compared is non-linguistic, using the default overloads can produce undesirable results, as the following attempt to perform a case-insensitive comparison of the strings "file" and "FILE" illustrates.</span></span>

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string fileUrl = "file";
      Thread.CurrentThread.CurrentCulture = new CultureInfo("en-US");
      Console.WriteLine("Culture = {0}",
                        Thread.CurrentThread.CurrentCulture.DisplayName);
      Console.WriteLine("(file == FILE) = {0}", 
                       fileUrl.StartsWith("FILE", true, null));
      Console.WriteLine();

      Thread.CurrentThread.CurrentCulture = new CultureInfo("tr-TR");
      Console.WriteLine("Culture = {0}",
                        Thread.CurrentThread.CurrentCulture.DisplayName);
      Console.WriteLine("(file == FILE) = {0}", 
                        fileUrl.StartsWith("FILE", true, null));
   }
}
// The example displays the following output:
//       Culture = English (United States)
//       (file == FILE) = True
//       
//       Culture = Turkish (Turkey)
//       (file == FILE) = False
```

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim fileUrl = "file"
      Thread.CurrentThread.CurrentCulture = New CultureInfo("en-US")
      Console.WriteLine("Culture = {0}", _
                        Thread.CurrentThread.CurrentCulture.DisplayName)
      Console.WriteLine("(file == FILE) = {0}", _ 
                       fileUrl.StartsWith("FILE", True, Nothing))
      Console.WriteLine()

      Thread.CurrentThread.CurrentCulture = New CultureInfo("tr-TR")
      Console.WriteLine("Culture = {0}", _
                        Thread.CurrentThread.CurrentCulture.DisplayName)
      Console.WriteLine("(file == FILE) = {0}", _ 
                        fileUrl.StartsWith("FILE", True, Nothing))
   End Sub
End Module
' The example displays the following output:
'       Culture = English (United States)
'       (file == FILE) = True
'       
'       Culture = Turkish (Turkey)
'       (file == FILE) = False
```

<span data-ttu-id="99b3a-202">Questo confronto può causare problemi significativi se le impostazioni cultura vengono usate inavvertitamente in impostazioni relative alla sicurezza, come nel seguente esempio.</span><span class="sxs-lookup"><span data-stu-id="99b3a-202">This comparison could cause significant problems if the culture is inadvertently used in security-sensitive settings, as in the following example.</span></span> <span data-ttu-id="99b3a-203">Una chiamata al metodo come `IsFileURI("file:")` restituisce `true`, se le impostazioni cultura correnti sono per la lingua inglese (Stati Uniti) oppure `false` se le impostazioni cultura correnti sono per la lingua turca.</span><span class="sxs-lookup"><span data-stu-id="99b3a-203">A method call such as `IsFileURI("file:")` returns `true` if the current culture is U.S. English, but `false` if the current culture is Turkish.</span></span> <span data-ttu-id="99b3a-204">Quindi, nei sistemi turchi, qualcuno potrebbe aggirare le misure di sicurezza che bloccano l'accesso agli URI senza distinzione tra maiuscole e minuscole che iniziano con "FILE:".</span><span class="sxs-lookup"><span data-stu-id="99b3a-204">Thus, on Turkish systems, someone could circumvent security measures that block access to case-insensitive URIs that begin with "FILE:".</span></span>

```csharp
public static bool IsFileURI(String path) 
{
   return path.StartsWith("FILE:", true, null);
}
```

```vb
Public Shared Function IsFileURI(path As String) As Boolean 
   Return path.StartsWith("FILE:", True, Nothing)
End Function
```

<span data-ttu-id="99b3a-205">In questo caso, poiché "file:" deve essere interpretato come un identificatore non linguistico e senza distinzione delle impostazioni cultura, il codice deve essere scritto come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="99b3a-205">In this case, because "file:" is meant to be interpreted as a non-linguistic, culture-insensitive identifier, the code should instead be written as shown in the following example.</span></span>

```csharp
public static bool IsFileURI(string path) 
{
   return path.StartsWith("FILE:", StringComparison.OrdinalIgnoreCase);
}
```

```vb
Public Shared Function IsFileURI(path As String) As Boolean 
    Return path.StartsWith("FILE:", StringComparison.OrdinalIgnoreCase)
End Function
```

## <a name="ordinal-string-operations"></a><span data-ttu-id="99b3a-206">Operazioni di stringa ordinali</span><span class="sxs-lookup"><span data-stu-id="99b3a-206">Ordinal String Operations</span></span>

<span data-ttu-id="99b3a-207">La specifica del valore [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) o [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) in una chiamata al metodo indica un confronto non linguistico in cui le funzionalità dei linguaggi naturali vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="99b3a-207">Specifying the [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) value in a method call signifies a non-linguistic comparison in which the features of natural languages are ignored.</span></span> <span data-ttu-id="99b3a-208">I metodi richiamati con questi valori [StringComparison](xref:System.StringComparison) basano le decisioni relative alle operazioni di stringa su confronti di byte semplici invece che sull'utilizzo di maiuscole e minuscole o di tabelle di equivalenza parametrizzate dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="99b3a-208">Methods that are invoked with these [StringComparison](xref:System.StringComparison) values base string operation decisions on simple byte comparisons instead of casing or equivalence tables that are parameterized by culture.</span></span> <span data-ttu-id="99b3a-209">In molti casi, questo approccio risulta più adatto per l'interpretazione desiderata delle stringhe e rende il codice più veloce e affidabile.</span><span class="sxs-lookup"><span data-stu-id="99b3a-209">In most cases, this approach best fits the intended interpretation of strings while making code faster and more reliable.</span></span> 

<span data-ttu-id="99b3a-210">I confronti ordinali sono confronti tra stringhe in cui ogni byte di ogni stringa viene confrontato senza interpretazione linguistica, ad esempio "windows" non corrisponde a "Windows".</span><span class="sxs-lookup"><span data-stu-id="99b3a-210">Ordinal comparisons are string comparisons in which each byte of each string is compared without linguistic interpretation; for example, "windows" does not match "Windows".</span></span> <span data-ttu-id="99b3a-211">Usare questo confronto quando il contesto impone l'esatta corrispondenza delle stringhe o richiede un criterio di corrispondenza conservativo.</span><span class="sxs-lookup"><span data-stu-id="99b3a-211">Use this comparison when the context dictates that strings should be matched exactly or demands conservative matching policy.</span></span> <span data-ttu-id="99b3a-212">Inoltre, il confronto ordinale è l'operazione di confronto più rapida perché non applica regole linguistiche quando determina un risultato.</span><span class="sxs-lookup"><span data-stu-id="99b3a-212">Additionally, ordinal comparison is the fastest comparison operation because it applies no linguistic rules when determining a result.</span></span>

<span data-ttu-id="99b3a-213">Le stringhe in .NET possono contenere caratteri null incorporati.</span><span class="sxs-lookup"><span data-stu-id="99b3a-213">Strings in .NET can contain embedded null characters.</span></span> <span data-ttu-id="99b3a-214">Una delle differenze più evidenti tra il confronto ordinale e quello con distinzione delle impostazioni cultura (inclusi i confronti che usano la lingua inglese) riguarda la gestione dei caratteri null incorporati in una stringa.</span><span class="sxs-lookup"><span data-stu-id="99b3a-214">One of the clearest differences between ordinal and culture-sensitive comparison (including comparisons that use the invariant culture) concerns the handling of embedded null characters in a string.</span></span> <span data-ttu-id="99b3a-215">Questi caratteri vengono ignorati quando si usano i metodi [String](xref:System.String) `Compare` e [String](xref:System.String) `Equals` per eseguire confronti con distinzione delle impostazioni cultura, inclusi i confronti che usano le impostazioni cultura per la lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="99b3a-215">These characters are ignored when you use the [String](xref:System.String) `Compare` and [String](xref:System.String) `Equals` methods to perform culture-sensitive comparisons (including comparisons that use the invariant culture).</span></span> <span data-ttu-id="99b3a-216">Di conseguenza, nei confronti con distinzione delle impostazioni cultura, le stringhe che contengono caratteri null incorporati e quelle che non li contengono possono essere considerate uguali.</span><span class="sxs-lookup"><span data-stu-id="99b3a-216">As a result, in culture-sensitive comparisons, strings that contain embedded null characters can be considered equal to strings that do not.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="99b3a-217">Sebbene i metodi di confronto tra stringhe ignorino i caratteri null incorporati, i metodi di ricerca delle stringhe, ad esempio [String.Contains](xref:System.String.Contains(System.String)), [String.EndsWith](xref:System.String.EndsWith(System.String)), [String.IndexOf](xref:System.String.IndexOf(System.Char)), [String.LastIndexOf](xref:System.String.LastIndexOf(System.String)) e [String.StartsWith](xref:System.String.StartsWith(System.String)) non li ignorano.</span><span class="sxs-lookup"><span data-stu-id="99b3a-217">Although string comparison methods disregard embedded null characters, string search methods such as [String.Contains](xref:System.String.Contains(System.String)), [String.EndsWith](xref:System.String.EndsWith(System.String)), [String.IndexOf](xref:System.String.IndexOf(System.Char)), [String.LastIndexOf](xref:System.String.LastIndexOf(System.String)), and [String.StartsWith](xref:System.String.StartsWith(System.String)) do not.</span></span> 

<span data-ttu-id="99b3a-218">L'esempio successivo esegue un confronto con distinzione delle impostazioni cultura della stringa "Aa" con una stringa simile che contiene diversi caratteri null incorporati tra "A" e "a" e mostra in che modo le due stringhe vengono considerate uguali..</span><span class="sxs-lookup"><span data-stu-id="99b3a-218">The following example performs a culture-sensitive comparison of the string "Aa" with a similar string that contains several embedded null characters between "A" and "a", and shows how the two strings are considered equal.</span></span> 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string str1 = "Aa";
      string str2 = "A" + new String('\u0000', 3) + "a";
      Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", 
                        str1, ShowBytes(str1), str2, ShowBytes(str2));
      Console.WriteLine("   With String.Compare:");
      Console.WriteLine("      Current Culture: {0}", 
                        String.Compare(str1, str2, StringComparison.CurrentCulture));
      Console.WriteLine("      Invariant Culture: {0}", 
                        String.Compare(str1, str2, StringComparison.InvariantCulture));

      Console.WriteLine("   With String.Equals:");
      Console.WriteLine("      Current Culture: {0}", 
                        String.Equals(str1, str2, StringComparison.CurrentCulture));
      Console.WriteLine("      Invariant Culture: {0}", 
                        String.Equals(str1, str2, StringComparison.InvariantCulture));
   }

   private static string ShowBytes(string str)
   {
      string hexString = String.Empty;
      for (int ctr = 0; ctr < str.Length; ctr++)
      {
         string result = String.Empty;
         result = Convert.ToInt32(str[ctr]).ToString("X4");
         result = " " + result.Substring(0,2) + " " + result.Substring(2, 2);
         hexString += result;
      }
      return hexString.Trim();
   }
}
// The example displays the following output:
//    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
//       With String.Compare:
//          Current Culture: 0
//          Invariant Culture: 0
//       With String.Equals:
//          Current Culture: True
//          Invariant Culture: True
```

```vb
Module Example
   Public Sub Main()
      Dim str1 As String = "Aa"
      Dim str2 As String = "A" + New String(Convert.ToChar(0), 3) + "a"
      Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", _
                        str1, ShowBytes(str1), str2, ShowBytes(str2))
      Console.WriteLine("   With String.Compare:")
      Console.WriteLine("      Current Culture: {0}", _
                        String.Compare(str1, str2, StringComparison.CurrentCulture))
      Console.WriteLine("      Invariant Culture: {0}", _
                        String.Compare(str1, str2, StringComparison.InvariantCulture))

      Console.WriteLine("   With String.Equals:")
      Console.WriteLine("      Current Culture: {0}", _
                        String.Equals(str1, str2, StringComparison.CurrentCulture))
      Console.WriteLine("      Invariant Culture: {0}", _
                        String.Equals(str1, str2, StringComparison.InvariantCulture))
   End Sub

   Private Function ShowBytes(str As String) As String
      Dim hexString As String = String.Empty
      For ctr As Integer = 0 To str.Length - 1
         Dim result As String = String.Empty
         result = Convert.ToInt32(str.Chars(ctr)).ToString("X4")
         result = " " + result.Substring(0,2) + " " + result.Substring(2, 2)
         hexString += result
      Next
      Return hexString.Trim()
   End Function
End Module
```

<span data-ttu-id="99b3a-219">Tuttavia, le stringhe non sono considerate uguali quando si usa il confronto ordinale, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="99b3a-219">However, the strings are not considered equal when you use ordinal comparison, as the following example shows.</span></span>

```csharp
Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", 
                  str1, ShowBytes(str1), str2, ShowBytes(str2));
Console.WriteLine("   With String.Compare:");
Console.WriteLine("      Ordinal: {0}", 
                  String.Compare(str1, str2, StringComparison.Ordinal));

Console.WriteLine("   With String.Equals:");
Console.WriteLine("      Ordinal: {0}", 
                  String.Equals(str1, str2, StringComparison.Ordinal));
// The example displays the following output:
//    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
//       With String.Compare:
//          Ordinal: 97
//       With String.Equals:
//          Ordinal: False
```

```vb
Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", _
                  str1, ShowBytes(str1), str2, ShowBytes(str2))
Console.WriteLine("   With String.Compare:")
Console.WriteLine("      Ordinal: {0}", _
                  String.Compare(str1, str2, StringComparison.Ordinal))

Console.WriteLine("   With String.Equals:")
Console.WriteLine("      Ordinal: {0}", _
                  String.Equals(str1, str2, StringComparison.Ordinal))
' The example displays the following output:
'    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
'       With String.Compare:
'          Ordinal: 97
'       With String.Equals:
'          Ordinal: False
```

<span data-ttu-id="99b3a-220">I confronti ordinali senza distinzione tra maiuscole e minuscole rappresentano il secondo approccio più conservativo.</span><span class="sxs-lookup"><span data-stu-id="99b3a-220">Case-insensitive ordinal comparisons are the next most conservative approach.</span></span> <span data-ttu-id="99b3a-221">Questi confronti ignorano quasi del tutto l'utilizzo di maiuscole e minuscole, ad esempio "windows" corrisponde a "Windows".</span><span class="sxs-lookup"><span data-stu-id="99b3a-221">These comparisons ignore most casing; for example, "windows" matches "Windows".</span></span> <span data-ttu-id="99b3a-222">Quando si usano i caratteri ASCII, questo criterio è equivalente a [StringComparison.Ordinal](xref:System.StringComparison.Ordinal), ma ignora il normale utilizzo di maiuscole e minuscole ASCII.</span><span class="sxs-lookup"><span data-stu-id="99b3a-222">When dealing with ASCII characters, this policy is equivalent to [StringComparison.Ordinal](xref:System.StringComparison.Ordinal), except that it ignores the usual ASCII casing.</span></span> <span data-ttu-id="99b3a-223">Quindi, qualsiasi carattere in [A, Z] (\u0041-\u005A) corrisponde al carattere corrispondente in [a,z] (\u0061-\007A).</span><span class="sxs-lookup"><span data-stu-id="99b3a-223">Therefore, any character in [A, Z] (\u0041-\u005A) matches the corresponding character in [a,z] (\u0061-\007A).</span></span> <span data-ttu-id="99b3a-224">L'utilizzo di maiuscole e minuscole al di fuori dell'intervallo ASCII usa le tabelle in lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="99b3a-224">Casing outside the ASCII range uses the invariant culture's tables.</span></span> <span data-ttu-id="99b3a-225">Pertanto, il confronto seguente:</span><span class="sxs-lookup"><span data-stu-id="99b3a-225">Therefore, the following comparison:</span></span>

```csharp
String.Compare(strA, strB, StringComparison.OrdinalIgnoreCase);
```

```vb
String.Compare(strA, strB, StringComparison.OrdinalIgnoreCase)
```

<span data-ttu-id="99b3a-226">è equivalente (ma più rapido) rispetto al confronto:</span><span class="sxs-lookup"><span data-stu-id="99b3a-226">is equivalent to (but faster than) this comparison:</span></span> 

```csharp
String.Compare(strA.ToUpperInvariant(), strB.ToUpperInvariant(), 
               StringComparison.Ordinal);
```

```vb
String.Compare(strA.ToUpperInvariant(), strB.ToUpperInvariant(), 
               StringComparison.Ordinal)
```

<span data-ttu-id="99b3a-227">Questi confronti sono comunque molto rapidi.</span><span class="sxs-lookup"><span data-stu-id="99b3a-227">These comparisons are still very fast.</span></span>

<span data-ttu-id="99b3a-228">[StringComparison.Ordinal](xref:System.StringComparison.Ordinal) e [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) usano entrambi direttamente i valori binari e sono più adatti per la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="99b3a-228">Both [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) and [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) use the binary values directly, and are best suited for matching.</span></span> <span data-ttu-id="99b3a-229">Se non si è sicuri delle impostazioni di confronto, usare uno di questi due valori.</span><span class="sxs-lookup"><span data-stu-id="99b3a-229">When you are not sure about your comparison settings, use one of these two values.</span></span> <span data-ttu-id="99b3a-230">Tuttavia, poiché eseguono un confronto byte per byte, l'ordinamento non viene eseguito linguisticamente (come in un dizionario inglese), ma in modo binario.</span><span class="sxs-lookup"><span data-stu-id="99b3a-230">However, because they perform a byte-by-byte comparison, they do not sort by a linguistic sort order (like an English dictionary) but by a binary sort order.</span></span> <span data-ttu-id="99b3a-231">Se visualizzati dagli utenti, i risultati possono sembrare strani in molti contesti.</span><span class="sxs-lookup"><span data-stu-id="99b3a-231">The results may look odd in most contexts if displayed to users.</span></span>

<span data-ttu-id="99b3a-232">La semantica ordinale è l'impostazione predefinita per gli overload [String](xref:System.String) `Equals` che non includono un argomento [StringComparison](xref:System.StringComparison) (incluso l'operatore di uguaglianza).</span><span class="sxs-lookup"><span data-stu-id="99b3a-232">Ordinal semantics are the default for [String](xref:System.String) `Equals` overloads that do not include a [StringComparison](xref:System.StringComparison) argument (including the equality operator).</span></span> <span data-ttu-id="99b3a-233">In ogni caso, si consiglia di chiamare un overload con un parametro [StringComparison](xref:System.StringComparison).</span><span class="sxs-lookup"><span data-stu-id="99b3a-233">In any case, we recommend that you call an overload that has a [StringComparison](xref:System.StringComparison) parameter.</span></span>

### <a name="string-operations-that-use-the-invariant-culture"></a><span data-ttu-id="99b3a-234">Operazioni di stringa che usano impostazioni cultura non dipendenti da paese/area geografica</span><span class="sxs-lookup"><span data-stu-id="99b3a-234">String operations that use the invariant culture</span></span>

<span data-ttu-id="99b3a-235">I confronti con le impostazioni cultura per la lingua inglese usano la proprietà [CompareInfo](xref:System.Globalization.CompareInfo) restituita dalla proprietà statica [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture).</span><span class="sxs-lookup"><span data-stu-id="99b3a-235">Comparisons with the invariant culture use the [CompareInfo](xref:System.Globalization.CompareInfo) property returned by the static [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) property.</span></span> <span data-ttu-id="99b3a-236">Questo comportamento è uguale in tutti i sistemi. Converte i caratteri al di fuori dell'intervallo in quelli che considera caratteri equivalenti in lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="99b3a-236">This behavior is the same on all systems; it translates any characters outside its range into what it believes are equivalent invariant characters.</span></span> <span data-ttu-id="99b3a-237">Questo criterio può essere utile per gestire il comportamento di un set di stringhe nelle impostazioni cultura, ma spesso produce risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="99b3a-237">This policy can be useful for maintaining one set of string behavior across cultures, but it often provides unexpected results.</span></span>

<span data-ttu-id="99b3a-238">I confronti senza distinzione tra maiuscole e minuscole con le impostazioni cultura per la lingua inglese usano la proprietà statica [CompareInfo](xref:System.Globalization.CompareInfo) restituita dalla proprietà statica [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) anche per le informazioni sul confronto.</span><span class="sxs-lookup"><span data-stu-id="99b3a-238">Case-insensitive comparisons with the invariant culture use the static [CompareInfo](xref:System.Globalization.CompareInfo) property returned by the static [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) property for comparison information as well.</span></span> <span data-ttu-id="99b3a-239">Le differenze tra maiuscole e minuscole in questi caratteri convertiti vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="99b3a-239">Any case differences among these translated characters are ignored.</span></span>

<span data-ttu-id="99b3a-240">L'oggetto [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) fa sì che il metodo [String](xref:System.String) `Compare` interpreti alcuni set di caratteri come equivalenti.</span><span class="sxs-lookup"><span data-stu-id="99b3a-240">The [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) object makes a [String](xref:System.String) `Compare` method interpret certain sets of characters as equivalent.</span></span> <span data-ttu-id="99b3a-241">Ad esempio, la seguente equivalenza è valida in lingua inglese:</span><span class="sxs-lookup"><span data-stu-id="99b3a-241">For example, the following equivalence is valid under the invariant culture:</span></span>

<span data-ttu-id="99b3a-242">InvariantCulture: a + ̊ = å</span><span class="sxs-lookup"><span data-stu-id="99b3a-242">InvariantCulture: a + ̊ = å</span></span>

<span data-ttu-id="99b3a-243">La lettera A minuscola latina "a" (\u0061) quando si trova accanto al carattere cerchio in alto "+ " ̊" (\u030a) viene interpretata come lettera A minuscola latina con il carattere cerchio in alto "å" (\u00e5).</span><span class="sxs-lookup"><span data-stu-id="99b3a-243">The latin small lette A character "a" (\u0061), when it is next to the combining ring above character "+ " ̊" (\u030a), is interpreted as the latin small letter A with ring above character "å" (\u00e5).</span></span> <span data-ttu-id="99b3a-244">Come mostrato nell'esempio seguente, questo comportamento è diverso dal confronto ordinale.</span><span class="sxs-lookup"><span data-stu-id="99b3a-244">As the following example shows, this behavior differs from ordinal comparison.</span></span>

```csharp
string separated = "\u0061\u030a";
string combined = "\u00e5";

Console.WriteLine("Equal sort weight of {0} and {1} using InvariantCulture: {2}",
                  separated, combined, 
                  String.Compare(separated, combined, 
                                 StringComparison.InvariantCulture) == 0);

Console.WriteLine("Equal sort weight of {0} and {1} using Ordinal: {2}",
                  separated, combined,
                  String.Compare(separated, combined, 
                                 StringComparison.Ordinal) == 0);
// The example displays the following output:
//    Equal sort weight of a° and å using InvariantCulture: True
//    Equal sort weight of a° and å using Ordinal: False 
```

```vb
Dim separated As String = ChrW(&h61) + ChrW(&h30a)
Dim combined As String = ChrW(&he5)

Console.WriteLine("Equal sort weight of {0} and {1} using InvariantCulture: {2}", _
                  separated, combined, _
                  String.Compare(separated, combined, _ 
                                 StringComparison.InvariantCulture) = 0)

Console.WriteLine("Equal sort weight of {0} and {1} using Ordinal: {2}", _
                  separated, combined, _
                  String.Compare(separated, combined, _
                                 StringComparison.Ordinal) = 0)
' The example displays the following output:
'    Equal sort weight of a° and å using InvariantCulture: True
'    Equal sort weight of a° and å using Ordinal: False
```

<span data-ttu-id="99b3a-245">Quando si interpretano i nomi di file, i cookie o qualsiasi altro elemento che può contenere un carattere come "å", i confronti ordinali offrono il comportamento più trasparente e appropriato.</span><span class="sxs-lookup"><span data-stu-id="99b3a-245">When interpreting file names, cookies, or anything else where a combination such as "å" can appear, ordinal comparisons still offer the most transparent and fitting behavior.</span></span>

<span data-ttu-id="99b3a-246">In realtà la lingua inglese ha poche proprietà che la rendono utile per il confronto.</span><span class="sxs-lookup"><span data-stu-id="99b3a-246">On balance, the invariant culture has very few properties that make it useful for comparison.</span></span> <span data-ttu-id="99b3a-247">Esegue il confronto in un modo linguisticamente rilevante, che non assicura un'equivalenza simbolica completa, ma non rappresenta la scelta ottimale per la visualizzazione nelle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="99b3a-247">It does comparison in a linguistically relevant manner, which prevents it from guaranteeing full symbolic equivalence, but it is not the choice for display in any culture.</span></span> <span data-ttu-id="99b3a-248">Ad esempio, se un file di dati di grandi dimensioni che contiene un elenco di identificatori ordinati per la visualizzazione viene associato a un'applicazione, per aggiungere elementi all'elenco è necessario l'inserimento con un ordinamento in lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="99b3a-248">For example, if a large data file that contains a list of sorted identifiers for display accompanies an application, adding to this list would require an insertion with invariant-style sorting.</span></span>

## <a name="choosing-a-stringcomparison-member-for-your-method-call"></a><span data-ttu-id="99b3a-249">Scelta di un membro StringComparison per la chiamata al metodo</span><span class="sxs-lookup"><span data-stu-id="99b3a-249">Choosing a StringComparison member for your method call</span></span>

<span data-ttu-id="99b3a-250">La tabella seguente mostra il mapping da un contesto di stringhe semantico a un membro dell'enumerazione [StringComparison](xref:System.StringComparison).</span><span class="sxs-lookup"><span data-stu-id="99b3a-250">The following table outlines the mapping from semantic string context to a [StringComparison](xref:System.StringComparison) enumeration member.</span></span>

<span data-ttu-id="99b3a-251">Dati</span><span class="sxs-lookup"><span data-stu-id="99b3a-251">Data</span></span> | <span data-ttu-id="99b3a-252">Comportamento</span><span class="sxs-lookup"><span data-stu-id="99b3a-252">Behavior</span></span> | <span data-ttu-id="99b3a-253">Valore System.StringComparison corrispondente</span><span class="sxs-lookup"><span data-stu-id="99b3a-253">Corresponding System.StringComparison value</span></span>
---- | -------- | -------------------------------------------
<span data-ttu-id="99b3a-254">Identificatori interni con distinzione tra maiuscole e minuscole, identificatori con distinzione tra maiuscole e minuscole in standard come XML e HTTP o impostazioni di sicurezza con distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="99b3a-254">Case-sensitive internal identifiers, case-sensitive identifiers in standards such as XML and HTTP, or case-sensitive security-related settings.</span></span> | <span data-ttu-id="99b3a-255">Identificatore non linguistico, con una corrispondenza esatta dei byte.</span><span class="sxs-lookup"><span data-stu-id="99b3a-255">A non-linguistic identifier, where bytes match exactly.</span></span> | [<span data-ttu-id="99b3a-256">StringComparison.Ordinal</span><span class="sxs-lookup"><span data-stu-id="99b3a-256">StringComparison.Ordinal</span></span>](xref:System.StringComparison.Ordinal)
<span data-ttu-id="99b3a-257">Identificatori interni senza distinzione tra maiuscole e minuscole, identificatori senza distinzione tra maiuscole e minuscole in standard come XML e HTTP, percorsi di file, chiavi e valori del Registro di sistema, variabili di ambiente, identificatori di risorse, ad esempio nomi di handle o impostazioni di sicurezza senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="99b3a-257">Case-insensitive internal identifiers, case-insensitive identifiers in standards such as XML and HTTP, file paths, registry keys and values, environment variables, resource identifiers (for example, handle names), or case-insensitive security-related settings.</span></span> | <span data-ttu-id="99b3a-258">Identificatore non linguistico, indipendente dalla distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="99b3a-258">A non-linguistic identifier, where case is irrelevant.</span></span> | [<span data-ttu-id="99b3a-259">StringComparison.OrdinalIgnoreCase</span><span class="sxs-lookup"><span data-stu-id="99b3a-259">StringComparison.OrdinalIgnoreCase</span></span>](xref:System.StringComparison.OrdinalIgnoreCase)
<span data-ttu-id="99b3a-260">Dati visualizzati all'utente o maggior parte dell'input utente.</span><span class="sxs-lookup"><span data-stu-id="99b3a-260">Data displayed to the user or most user input.</span></span> | <span data-ttu-id="99b3a-261">Dati che richiedono personalizzazioni linguistiche locali.</span><span class="sxs-lookup"><span data-stu-id="99b3a-261">Data that requires local linguistic customs.</span></span> | <span data-ttu-id="99b3a-262">[StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) o [CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase)</span><span class="sxs-lookup"><span data-stu-id="99b3a-262">[StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) or [CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase)</span></span>

## <a name="common-string-comparison-methods"></a><span data-ttu-id="99b3a-263">Metodi comuni per il confronto tra stringhe</span><span class="sxs-lookup"><span data-stu-id="99b3a-263">Common string comparison methods</span></span>

<span data-ttu-id="99b3a-264">Le sezioni seguenti descrivono i metodi più comuni per il confronto tra stringhe.</span><span class="sxs-lookup"><span data-stu-id="99b3a-264">The following sections describe the methods that are most commonly used for string comparison.</span></span>

### <a name="stringcompare"></a><span data-ttu-id="99b3a-265">String.Compare</span><span class="sxs-lookup"><span data-stu-id="99b3a-265">String.Compare</span></span>

<span data-ttu-id="99b3a-266">Interpretazione predefinita: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="99b3a-266">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="99b3a-267">Poiché si tratta dell'operazione più importante per l'interpretazione della stringa, tutte le istanze di queste chiamate al metodo devono essere esaminate per determinare se le stringhe devono essere interpretate in base alle impostazioni cultura correnti o devono essere dissociate dalle impostazioni cultura (simbolicamente).</span><span class="sxs-lookup"><span data-stu-id="99b3a-267">As the operation most central to string interpretation, all instances of these method calls should be examined to determine whether strings should be interpreted according to the current culture, or dissociated from the culture (symbolically).</span></span> <span data-ttu-id="99b3a-268">In genere, si tratta del secondo caso e deve pertanto essere usato un confronto [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).</span><span class="sxs-lookup"><span data-stu-id="99b3a-268">Typically, it is the latter, and a [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) comparison should be used instead.</span></span>

<span data-ttu-id="99b3a-269">La classe [System.Globalization.CompareInfo](xref:System.Globalization.CompareInfo), restituita dalla proprietà [CultureInfo.CompareInfo](xref:System.Globalization.CultureInfo.CompareInfo), include anche un metodo [Compare](xref:System.Globalization.CompareInfo.Compare(System.String,System.Int32,System.String,System.Int32,System.Globalization.CompareOptions)) che offre numerose opzioni di corrispondenza (ordinale, con esclusione degli spazi vuoti, con esclusione del tipo Kana e così via) mediante l'enumerazione flag [CompareOptions](xref:System.Globalization.CompareOptions).</span><span class="sxs-lookup"><span data-stu-id="99b3a-269">The [System.Globalization.CompareInfo](xref:System.Globalization.CompareInfo) class, which is returned by the [CultureInfo.CompareInfo](xref:System.Globalization.CultureInfo.CompareInfo) property, also includes a [Compare](xref:System.Globalization.CompareInfo.Compare(System.String,System.Int32,System.String,System.Int32,System.Globalization.CompareOptions)) method that provides a large number of matching options (ordinal, ignoring white space, ignoring kana type, and so on) by means of the [CompareOptions](xref:System.Globalization.CompareOptions) flag enumeration.</span></span> 

### <a name="stringcompareto"></a><span data-ttu-id="99b3a-270">String.CompareTo</span><span class="sxs-lookup"><span data-stu-id="99b3a-270">String.CompareTo</span></span>

<span data-ttu-id="99b3a-271">Interpretazione predefinita: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="99b3a-271">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="99b3a-272">Questo metodo attualmente non offre un overload che specifica un tipo [StringComparison](xref:System.StringComparison).</span><span class="sxs-lookup"><span data-stu-id="99b3a-272">This method does not currently offer an overload that specifies a [StringComparison](xref:System.StringComparison) type.</span></span> <span data-ttu-id="99b3a-273">In genere è possibile convertire questo metodo nel tipo consigliato [String.Compare(String, String, StringComparison)](xref:System.String.Compare(System.String,System.String,System.StringComparison)).</span><span class="sxs-lookup"><span data-stu-id="99b3a-273">It is usually possible to convert this method to the recommended [String.Compare(String, String, StringComparison)](xref:System.String.Compare(System.String,System.String,System.StringComparison)) form.</span></span>

<span data-ttu-id="99b3a-274">I tipi che implementano le interfacce [IComparable](xref:System.IComparable) e [IComparable&lt;T&gt;](xref:System.IComparable%601) implementano questo metodo.</span><span class="sxs-lookup"><span data-stu-id="99b3a-274">Types that implement the [IComparable](xref:System.IComparable) and [IComparable&lt;T&gt;](xref:System.IComparable%601) interfaces implement this method.</span></span> <span data-ttu-id="99b3a-275">Poiché non offre l'opzione di un parametro [StringComparison](xref:System.StringComparison), l'implementazione dei tipi spesso lascia specificare all'utente [StringComparer](xref:System.StringComparer) nel proprio costruttore.</span><span class="sxs-lookup"><span data-stu-id="99b3a-275">Because it does not offer the option of a [StringComparison](xref:System.StringComparison) parameter, implementing types often let the user specify a [StringComparer](xref:System.StringComparer) in their constructor.</span></span> <span data-ttu-id="99b3a-276">L'esempio seguente definisce una classe `FileName` il cui costruttore include un parametro [StringComparer](xref:System.StringComparer).</span><span class="sxs-lookup"><span data-stu-id="99b3a-276">The following example defines a `FileName` class whose class constructor includes a [StringComparer](xref:System.StringComparer) parameter.</span></span> <span data-ttu-id="99b3a-277">L'oggetto [StringComparer](xref:System.StringComparer) viene quindi usato nel metodo `FileName.CompareTo`.</span><span class="sxs-lookup"><span data-stu-id="99b3a-277">This [StringComparer](xref:System.StringComparer) object is then used in the `FileName.CompareTo` method.</span></span>

```csharp
using System;

public class FileName : IComparable
{
   string fname;
   StringComparer comparer; 

   public FileName(string name, StringComparer comparer)
   {
      if (String.IsNullOrEmpty(name))
         throw new ArgumentNullException("name");

      this.fname = name;

      if (comparer != null)
         this.comparer = comparer;
      else
         this.comparer = StringComparer.OrdinalIgnoreCase;
   }

   public string Name
   {
      get { return fname; }
   }

   public int CompareTo(object obj)
   {
      if (obj == null) return 1;

      if (! (obj is FileName))
         return comparer.Compare(this.fname, obj.ToString());
      else
         return comparer.Compare(this.fname, ((FileName) obj).Name);
   }
}
```

```vb
Public Class FileName : Implements IComparable
   Dim fname As String
   Dim comparer As StringComparer 

   Public Sub New(name As String, comparer As StringComparer)
      If String.IsNullOrEmpty(name) Then
         Throw New ArgumentNullException("name")
      End If

      Me.fname = name

      If comparer IsNot Nothing Then
         Me.comparer = comparer
      Else
         Me.comparer = StringComparer.OrdinalIgnoreCase
      End If      
   End Sub

   Public ReadOnly Property Name As String
      Get
         Return fname
      End Get   
   End Property

   Public Function CompareTo(obj As Object) As Integer _
          Implements IComparable.CompareTo
      If obj Is Nothing Then Return 1

      If Not TypeOf obj Is FileName Then
         obj = obj.ToString()
      Else
         obj = CType(obj, FileName).Name
      End If         
      Return comparer.Compare(Me.fname, obj)
   End Function
End Class
```

### <a name="stringequals"></a><span data-ttu-id="99b3a-278">String.Equals</span><span class="sxs-lookup"><span data-stu-id="99b3a-278">String.Equals</span></span>

<span data-ttu-id="99b3a-279">Interpretazione predefinita: [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).</span><span class="sxs-lookup"><span data-stu-id="99b3a-279">Default interpretation: [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).</span></span>

<span data-ttu-id="99b3a-280">La classe [String](xref:System.String) consente di eseguire un test di uguaglianza chiamando gli overload del metodo `Equals` dell'istanza o statici oppure usando l'operatore di uguaglianza statico.</span><span class="sxs-lookup"><span data-stu-id="99b3a-280">The [String](xref:System.String) class lets you test for equality by calling either the static or instance `Equals` method overloads, or by using the static equality operator.</span></span> <span data-ttu-id="99b3a-281">Gli overload e l'operatore usano il confronto ordinale per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="99b3a-281">The overloads and operator use ordinal comparison by default.</span></span> <span data-ttu-id="99b3a-282">Tuttavia, si consiglia di chiamare comunque un overload che specifichi esplicitamente il tipo [StringComparison](xref:System.StringComparison) anche se si vuole eseguire un confronto ordinale; questo semplifica la ricerca di codice per una determinata interpretazione della stringa.</span><span class="sxs-lookup"><span data-stu-id="99b3a-282">However, we still recommend that you call an overload that explicitly specifies the [StringComparison](xref:System.StringComparison) type even if you want to perform an ordinal comparison; this makes it easier to search code for a certain string interpretation.</span></span> 

### <a name="stringtoupper-and-stringtolower"></a><span data-ttu-id="99b3a-283">String.ToUpper e String.ToLower</span><span class="sxs-lookup"><span data-stu-id="99b3a-283">String.ToUpper and String.ToLower</span></span>

<span data-ttu-id="99b3a-284">Interpretazione predefinita: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="99b3a-284">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="99b3a-285">Prestare attenzione quando si usano questi metodi perché l'utilizzo forzato di maiuscole o minuscole in una stringa è una procedura usata spesso come normalizzazione minore per confrontare stringhe indipendentemente dalla distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="99b3a-285">You should be careful when you use these methods, because forcing a string to a uppercase or lowercase is often used as a small normalization for comparing strings regardless of case.</span></span> <span data-ttu-id="99b3a-286">In questo caso, valutare l'uso di un confronto senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="99b3a-286">If so, consider using a case-insensitive comparison.</span></span> 

<span data-ttu-id="99b3a-287">Sono anche disponibili i metodi [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) e [String.ToLowerInvariant](xref:System.String.ToLowerInvariant).</span><span class="sxs-lookup"><span data-stu-id="99b3a-287">The [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) and [String.ToLowerInvariant](xref:System.String.ToLowerInvariant) methods are also available.</span></span> <span data-ttu-id="99b3a-288">[ToUpperInvariant](xref:System.String.ToUpperInvariant) è la modalità standard di normalizzazione dei caratteri maiuscoli e minuscoli.</span><span class="sxs-lookup"><span data-stu-id="99b3a-288">[ToUpperInvariant](xref:System.String.ToUpperInvariant) is the standard way to normalize case.</span></span> <span data-ttu-id="99b3a-289">A livello di comportamento, i confronti eseguiti usando [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) corrispondono alla composizione di due chiamate: la chiamata a [ToUpperInvariant](xref:System.String.ToUpperInvariant) in entrambi gli argomenti di stringa e l'esecuzione di un confronto con [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).</span><span class="sxs-lookup"><span data-stu-id="99b3a-289">Comparisons made using [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) are behaviorally the composition of two calls: calling [ToUpperInvariant](xref:System.String.ToUpperInvariant) on both string arguments, and doing a comparison using [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).</span></span>

<span data-ttu-id="99b3a-290">Sono disponibili anche overload per la conversione in maiuscole e minuscole in determinate impostazioni cultura, passando un oggetto [CultureInfo](xref:System.Globalization.CultureInfo) che rappresenta le specifiche impostazioni cultura al metodo.</span><span class="sxs-lookup"><span data-stu-id="99b3a-290">Overloads are also available for converting to uppercase and lowercase in a specific culture, by passing a [CultureInfo](xref:System.Globalization.CultureInfo) object that represents that culture to the method.</span></span>

### <a name="chartoupper-and-chartolower"></a><span data-ttu-id="99b3a-291">Char.ToUpper e Char.ToLower</span><span class="sxs-lookup"><span data-stu-id="99b3a-291">Char.ToUpper and Char.ToLower</span></span>

<span data-ttu-id="99b3a-292">Interpretazione predefinita: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="99b3a-292">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="99b3a-293">Questi metodi funzionano in modo simile ai metodi [String.ToUpper](xref:System.String.ToUpper) e [String.ToLower](xref:System.String.ToLower) descritti nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="99b3a-293">These methods work similarly to the [String.ToUpper](xref:System.String.ToUpper) and [String.ToLower](xref:System.String.ToLower) methods described in the previous section.</span></span>

### <a name="stringstartswith-and-stringendswith"></a><span data-ttu-id="99b3a-294">String.StartsWith e String.EndsWith</span><span class="sxs-lookup"><span data-stu-id="99b3a-294">String.StartsWith and String.EndsWith</span></span>

<span data-ttu-id="99b3a-295">Interpretazione predefinita: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="99b3a-295">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="99b3a-296">Per impostazione predefinita, entrambi i metodi eseguono un confronto con distinzione delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="99b3a-296">By default, both of these methods perform a culture-sensitive comparison.</span></span>

### <a name="stringindexof-and-stringlastindexof"></a><span data-ttu-id="99b3a-297">String.IndexOf e String.LastIndexOf</span><span class="sxs-lookup"><span data-stu-id="99b3a-297">String.IndexOf and String.LastIndexOf</span></span>

<span data-ttu-id="99b3a-298">Interpretazione predefinita: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="99b3a-298">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="99b3a-299">La modalità di esecuzione dei confronti con gli overload predefiniti di questi metodi manca di coerenza.</span><span class="sxs-lookup"><span data-stu-id="99b3a-299">There is a lack of consistency in how the default overloads of these methods perform comparisons.</span></span> <span data-ttu-id="99b3a-300">Tutti i metodi [String](xref:System.String) `IndexOf` e [String](xref:System.String) `LastIndexOf` che includono un parametro [Char](xref:System.Char) eseguono un confronto ordinale, ma i metodi predefiniti [String](xref:System.String) `IndexOf` e [String`](xref:System.String) `LastIndexOf\` che includono un parametro [String](xref:System.String) eseguono un confronto con distinzione delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="99b3a-300">All [String](xref:System.String) `IndexOf` and [String](xref:System.String) `LastIndexOf` methods that include a [Char](xref:System.Char) parameter perform an ordinal comparison, but the default [String](xref:System.String) `IndexOf` and [String`](xref:System.String) `LastIndexOf\` methods that include a [String](xref:System.String) parameter perform a culture-sensitive comparison.</span></span> 

<span data-ttu-id="99b3a-301">Se si chiama il metodo ` `IndexOf` or `LastIndexOf\` e si passa una stringa da individuare nell'istanza corrente, si consiglia di chiamare un overload che specifichi esplicitamente il tipo [StringComparison](xref:System.StringComparison).</span><span class="sxs-lookup"><span data-stu-id="99b3a-301">If you call ` `IndexOf` or `LastIndexOf\` method and pass it a string to locate in the current instance, we recommend that you call an overload that explicitly specifies the [StringComparison](xref:System.StringComparison) type.</span></span> <span data-ttu-id="99b3a-302">Gli overload che includono un argomento [Char](xref:System.Char) non consentono di specificare un tipo [StringComparison](xref:System.StringComparison).</span><span class="sxs-lookup"><span data-stu-id="99b3a-302">The overloads that include a [Char](xref:System.Char) argument do not allow you to specify a [StringComparison](xref:System.StringComparison) type.</span></span>

## <a name="methods-that-perform-string-comparison-indirectly"></a><span data-ttu-id="99b3a-303">Metodi che eseguono indirettamente il confronto tra stringhe</span><span class="sxs-lookup"><span data-stu-id="99b3a-303">Methods that perform string comparison indirectly</span></span>

<span data-ttu-id="99b3a-304">Alcuni metodi non di tipo stringa in cui il confronto tra stringhe rappresenta l'operazione più importante usano il tipo [StringComparer](xref:System.StringComparer).</span><span class="sxs-lookup"><span data-stu-id="99b3a-304">Some non-string methods that have string comparison as a central operation use the [StringComparer](xref:System.StringComparer) type.</span></span> <span data-ttu-id="99b3a-305">La classe [StringComparer](xref:System.StringComparer) include quattro proprietà statiche che restituiscono istanze [StringComparer](xref:System.StringComparer) i cui metodi `Compare` eseguono i tipi di confronto tra stringhe seguenti:</span><span class="sxs-lookup"><span data-stu-id="99b3a-305">The [StringComparer](xref:System.StringComparer) class includes four static properties that return [StringComparer](xref:System.StringComparer) instances whose `Compare` methods perform the following types of string comparisons:</span></span>

* <span data-ttu-id="99b3a-306">Confronti tra stringhe con distinzione delle impostazioni cultura usando le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="99b3a-306">Culture-sensitive string comparisons using the current culture.</span></span> <span data-ttu-id="99b3a-307">Questo oggetto [StringComparer](xref:System.StringComparer) è restituito dalla proprietà [StringComparer.CurrentCulture](xref:System.StringComparer.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="99b3a-307">This [StringComparer](xref:System.StringComparer) object is returned by the [StringComparer.CurrentCulture](xref:System.StringComparer.CurrentCulture) property.</span></span>

* <span data-ttu-id="99b3a-308">Confronti senza distinzione tra maiuscole e minuscole usando le impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="99b3a-308">Case-insensitive comparisons using the current culture.</span></span> <span data-ttu-id="99b3a-309">Questo oggetto [StringComparer](xref:System.StringComparer) è restituito dalla proprietà [StringComparer.CurrentCultureIgnoreCase](xref:System.StringComparer.CurrentCultureIgnoreCase).</span><span class="sxs-lookup"><span data-stu-id="99b3a-309">This [StringComparer](xref:System.StringComparer) object is returned by the [StringComparer.CurrentCultureIgnoreCase](xref:System.StringComparer.CurrentCultureIgnoreCase) property.</span></span>

* <span data-ttu-id="99b3a-310">Confronto ordinale.</span><span class="sxs-lookup"><span data-stu-id="99b3a-310">Ordinal comparison.</span></span> <span data-ttu-id="99b3a-311">Questo oggetto [StringComparer](xref:System.StringComparer) è restituito dalla proprietà [StringComparer.Ordinal](xref:System.StringComparer.Ordinal).</span><span class="sxs-lookup"><span data-stu-id="99b3a-311">This [StringComparer](xref:System.StringComparer) object is returned by the [StringComparer.Ordinal](xref:System.StringComparer.Ordinal) property.</span></span> 

* <span data-ttu-id="99b3a-312">Confronto ordinale senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="99b3a-312">Case-insensitive ordinal comparison.</span></span> <span data-ttu-id="99b3a-313">Questo oggetto [StringComparer](xref:System.StringComparer) è restituito dalla proprietà [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase).</span><span class="sxs-lookup"><span data-stu-id="99b3a-313">This [StringComparer](xref:System.StringComparer) object is returned by the [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase) property.</span></span>

### <a name="arraysort-and-arraybinarysearch"></a><span data-ttu-id="99b3a-314">Array.Sort e Array.BinarySearch</span><span class="sxs-lookup"><span data-stu-id="99b3a-314">Array.Sort and Array.BinarySearch</span></span>

<span data-ttu-id="99b3a-315">Interpretazione predefinita: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="99b3a-315">Default interpretation: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).</span></span>

<span data-ttu-id="99b3a-316">Quando si archiviano dati in una raccolta o si leggono dati persistenti da un file o da un database nella raccolta, la modifica delle impostazioni cultura correnti può invalidare le invarianti nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="99b3a-316">When you store any data in a collection, or read persisted data from a file or database into a collection, switching the current culture can invalidate the invariants in the collection.</span></span> <span data-ttu-id="99b3a-317">Il metodo [Array.BinarySearch](xref:System.Array.BinarySearch(System.Array,System.Object)) presuppone che gli elementi nella matrice da cercare siano già ordinati.</span><span class="sxs-lookup"><span data-stu-id="99b3a-317">The [Array.BinarySearch](xref:System.Array.BinarySearch(System.Array,System.Object)) method assumes that the elements in the array to be searched are already sorted.</span></span> <span data-ttu-id="99b3a-318">Per ordinare qualsiasi elemento di tipo stringa nella matrice, il metodo [Array.Sort](xref:System.Array.Sort(System.Array)) chiama il metodo [String] `Compare` per ordinare i singoli elementi.</span><span class="sxs-lookup"><span data-stu-id="99b3a-318">To sort any string element in the array, the [Array.Sort](xref:System.Array.Sort(System.Array)) method calls the [String] `Compare` method to order individual elements.</span></span> <span data-ttu-id="99b3a-319">L'uso di un operatore di confronto con distinzione delle impostazioni cultura può essere pericoloso se le impostazioni cultura vengono modificate tra l'ordinamento della matrice e la ricerca dei contenuti.</span><span class="sxs-lookup"><span data-stu-id="99b3a-319">Using a culture-sensitive comparer can be dangerous if the culture changes between the time that the array is sorted and its contents are searched.</span></span> <span data-ttu-id="99b3a-320">Nel codice seguente, ad esempio, le operazioni di archiviazione e recupero vengono eseguite nell'operatore di confronto fornito in modo implicito dalla proprietà `Thread.CurrentThread.CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="99b3a-320">For example, in the following code, storage and retrieval operate on the comparer that is provided implicitly by the `Thread.CurrentThread.CurrentCulture` property.</span></span> <span data-ttu-id="99b3a-321">Se le impostazioni cultura possono cambiare tra le chiamate a `StoreNames` e `DoesNameExist` e, in particolare, se il contenuto della matrice viene conservato tra le due chiamate al metodo, è possibile che la ricerca binaria non riesca.</span><span class="sxs-lookup"><span data-stu-id="99b3a-321">If the culture can change between the calls to `StoreNames` and `DoesNameExist`, and especially if the array contents are persisted somewhere between the two method calls, the binary search may fail.</span></span> 

```csharp
// Incorrect.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names); // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name) >= 0);  // Line B.
}
```

```vb
' Incorrect.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names)          ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name) >= 0      ' Line B.
End Function
```

<span data-ttu-id="99b3a-322">L'esempio seguente mostra una variazione consigliata che usa lo stesso metodo di confronto ordinale (senza distinzione delle impostazioni cultura) sia per l'ordinamento che per la ricerca nella matrice.</span><span class="sxs-lookup"><span data-stu-id="99b3a-322">A recommended variation appears in the following example, which uses the same ordinal (culture-insensitive) comparison method both to sort and to search the array.</span></span> <span data-ttu-id="99b3a-323">Il codice modificato si riflette nelle righe identificate con `Line A` e `Line B` nei due esempi.</span><span class="sxs-lookup"><span data-stu-id="99b3a-323">The change code is reflected in the lines labeled `Line A` and `Line B` in the two examples.</span></span>

```csharp
// Correct.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names, StringComparer.Ordinal);  // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name, StringComparer.Ordinal) >= 0);  // Line B.
}
```

```vb
' Correct.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names, StringComparer.Ordinal)           ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name, StringComparer.Ordinal) >= 0      ' Line B.
End Function
```

<span data-ttu-id="99b3a-324">Se i dati vengono conservati e spostati nelle impostazioni cultura e l'ordinamento viene usato per presentare i dati all'utente, potrebbe esser opportuno usare `StringComparison.InvariantCulture`, che garantisce un output utente migliore dal punto di vista linguistico ma non viene interessato dalle modifiche nelle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="99b3a-324">If this data is persisted and moved across cultures, and sorting is used to present this data to the user, you might consider using `StringComparison.InvariantCulture`, which operates linguistically for better user output but is unaffected by changes in culture.</span></span> <span data-ttu-id="99b3a-325">L'esempio seguente modifica i due esempi precedenti per usare la lingua inglese per l'ordinamento e la ricerca della matrice.</span><span class="sxs-lookup"><span data-stu-id="99b3a-325">The following example modifies the two previous examples to use the invariant culture for sorting and searching the array.</span></span>

```csharp
// Correct.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names, StringComparer.InvariantCulture);  // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name, StringComparer.InvariantCulture) >= 0);  // Line B.
}
```

```vb
' Correct.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names, StringComparer.InvariantCulture)           ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name, StringComparer.InvariantCulture) >= 0      ' Line B.
End Function
```

### <a name="collections-example-hashtable-constructor"></a><span data-ttu-id="99b3a-326">Esempio di raccolte: costruttore Hashtable</span><span class="sxs-lookup"><span data-stu-id="99b3a-326">Collections Example: Hashtable Constructor</span></span>

<span data-ttu-id="99b3a-327">L'esecuzione dell'hashing nelle stringhe fornisce un secondo esempio di operazione interessata dal modo in cui vengono confrontate le stringhe.</span><span class="sxs-lookup"><span data-stu-id="99b3a-327">Hashing strings provides a second example of an operation that is affected by the way in which strings are compared.</span></span> 

<span data-ttu-id="99b3a-328">L'esempio seguente crea un'istanza dell'oggetto [Hashtable](xref:System.Collections.Hashtable) passando l'oggetto [StringComparer](xref:System.StringComparer) restituito dalla proprietà [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase).</span><span class="sxs-lookup"><span data-stu-id="99b3a-328">The following example instantiates a [Hashtable](xref:System.Collections.Hashtable) object by passing it the [StringComparer](xref:System.StringComparer) object that is returned by the [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase) property.</span></span> <span data-ttu-id="99b3a-329">Poiché una classe [StringComparer](xref:System.StringComparer) derivata da [StringComparer](xref:System.StringComparer) implementa l'interfaccia [IEqualityComparer](xref:System.Collections.IEqualityComparer), il metodo [GetHashCode](xref:System.Collections.IEqualityComparer) viene usato per calcolare il codice hash delle stringhe nella tabella hash.</span><span class="sxs-lookup"><span data-stu-id="99b3a-329">Because a class [StringComparer](xref:System.StringComparer) that is derived from [StringComparer](xref:System.StringComparer) implements the [IEqualityComparer](xref:System.Collections.IEqualityComparer) interface, its [GetHashCode](xref:System.Collections.IEqualityComparer) method is used to compute the hash code of strings in the hash table.</span></span>

```csharp
const int initialTableCapacity = 100;
Hashtable h;

public void PopulateFileTable(string directory)
{
   h = new Hashtable(initialTableCapacity, 
                     StringComparer.OrdinalIgnoreCase);

   foreach (string file in Directory.GetFiles(directory))
         h.Add(file, File.GetCreationTime(file));
}

public void PrintCreationTime(string targetFile)
{
   Object dt = h[targetFile];
   if (dt != null)
   {
      Console.WriteLine("File {0} was created at time {1}.",
         targetFile, 
         (DateTime) dt);
   }
   else
   {
      Console.WriteLine("File {0} does not exist.", targetFile);
   }
}
```

```vb
Const initialTableCapacity As Integer = 100
Dim h As Hashtable

Public Sub PopulateFileTable(dir As String)
   h = New Hashtable(initialTableCapacity, _
                     StringComparer.OrdinalIgnoreCase)

   For Each filename As String In Directory.GetFiles(dir)
      h.Add(filename, File.GetCreationTime(filename))
   Next                        
End Sub

Public Sub PrintCreationTime(targetFile As String)
   Dim dt As Object = h(targetFile)
   If dt IsNot Nothing Then
      Console.WriteLine("File {0} was created at {1}.", _
         targetFile, _
         CDate(dt))
   Else
      Console.WriteLine("File {0} does not exist.", targetFile)
   End If
End Sub  
```

## <a name="displaying-and-persisting-formatted-data"></a><span data-ttu-id="99b3a-330">Visualizzazione e conservazione dei dati formattati</span><span class="sxs-lookup"><span data-stu-id="99b3a-330">Displaying and persisting formatted data</span></span>

<span data-ttu-id="99b3a-331">Quando si consente agli utenti di visualizzare dati non di tipo stringa, come numeri e date e ore, formattarli usando le impostazioni cultura dell'utente.</span><span class="sxs-lookup"><span data-stu-id="99b3a-331">When you display non-string data such as numbers and dates and times to users, format them by using the user's cultural settings.</span></span> <span data-ttu-id="99b3a-332">Per impostazione predefinita, il metodo [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) e i metodi `ToString` dei tipi numerici e dei tipi data e ora usano le impostazioni cultura del thread corrente per le operazioni di formattazione.</span><span class="sxs-lookup"><span data-stu-id="99b3a-332">By default, the [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) method and the `ToString` methods of the numeric types and the date and time types use the current thread culture for formatting operations.</span></span> <span data-ttu-id="99b3a-333">Per specificare esplicitamente che il metodo di formattazione deve usare le impostazioni cultura correnti, è possibile chiamare un overload di un metodo di formattazione con un parametro provider, ad esempio [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) o [DateTime.ToString(IFormatProvider)](xref:System.DateTime.ToString(System.IFormatProvider)) e passare la proprietà [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture).</span><span class="sxs-lookup"><span data-stu-id="99b3a-333">To explicitly specify that the formatting method should use the current culture, you can call an overload of a formatting method that has a provider parameter, such as [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) or [DateTime.ToString(IFormatProvider)](xref:System.DateTime.ToString(System.IFormatProvider)), and pass it the [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture) property.</span></span> 

<span data-ttu-id="99b3a-334">È possibile conservare i dati non di tipo stringa come dati binari o formattati.</span><span class="sxs-lookup"><span data-stu-id="99b3a-334">You can persist non-string data either as binary data or as formatted data.</span></span> <span data-ttu-id="99b3a-335">Se si sceglie di salvarli come dati formattati, è necessario chiamare un overload del metodo di formattazione che include un parametro *provider* e passare la proprietà [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture).</span><span class="sxs-lookup"><span data-stu-id="99b3a-335">If you choose to save it as formatted data, you should call a formatting method overload that includes a *provider* parameter and pass it the [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) property.</span></span> <span data-ttu-id="99b3a-336">La lingua inglese fornisce un formato coerente per i dati formattati, indipendente dalle impostazioni cultura e dal computer.</span><span class="sxs-lookup"><span data-stu-id="99b3a-336">The invariant culture provides a consistent format for formatted data that is independent of culture and machine.</span></span> <span data-ttu-id="99b3a-337">Al contrario, conservare i dati formattati con impostazioni cultura diverse dalla lingua inglese presenta diverse limitazioni:</span><span class="sxs-lookup"><span data-stu-id="99b3a-337">In contrast, persisting data that is formatted by using cultures other than the invariant culture has a number of limitations:</span></span> 

* <span data-ttu-id="99b3a-338">È probabile che i dati non saranno utilizzabili se vengono recuperati in un sistema con impostazioni cultura diverse oppure se l'utente del sistema corrente modifica le impostazioni cultura correnti e prova a recuperare i dati.</span><span class="sxs-lookup"><span data-stu-id="99b3a-338">The data is likely to be unusable if it is retrieved on a system that has a different culture, or if the user of the current system changes the current culture and tries to retrieve the data.</span></span> 

* <span data-ttu-id="99b3a-339">Le proprietà delle impostazioni cultura in uno specifico computer possono essere diverse rispetto ai valori standard.</span><span class="sxs-lookup"><span data-stu-id="99b3a-339">The properties of a culture on a specific computer can differ from standard values.</span></span> <span data-ttu-id="99b3a-340">Un utente può personalizzare in qualsiasi momento le impostazioni di visualizzazione con distinzione delle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="99b3a-340">At any time, a user can customize culture-sensitive display settings.</span></span> <span data-ttu-id="99b3a-341">Per questo motivo, i dati formattati salvati in un sistema potrebbero non essere leggibili dopo che un utente personalizza le impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="99b3a-341">Because of this, formatted data that is saved on a system may not be readable after the user customizes cultural settings.</span></span> <span data-ttu-id="99b3a-342">La portabilità dei dati formattati tra i vari computer potrebbe risultare ancora più limitata.</span><span class="sxs-lookup"><span data-stu-id="99b3a-342">The portability of formatted data across computers is likely to be even more limited.</span></span> 

* <span data-ttu-id="99b3a-343">Gli standard internazionali, regionali o nazionali che regolano la formattazione dei numeri o delle date e delle ore cambiano nel tempo e queste modifiche vengono incorporate negli aggiornamenti del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="99b3a-343">International, regional, or national standards that govern the formatting of numbers or dates and times change over time, and these changes are incorporated into operating system updates.</span></span> <span data-ttu-id="99b3a-344">Quando le convenzioni di formattazione vengono modificate, i dati formattati con le convenzioni precedenti possono diventare illeggibili.</span><span class="sxs-lookup"><span data-stu-id="99b3a-344">When formatting conventions change, data that was formatted by using the previous conventions may become unreadable.</span></span> 

<span data-ttu-id="99b3a-345">L'esempio seguente illustra la limitazione della portabilità causata dall'uso della formattazione con distinzione delle impostazioni cultura per la persistenza dei dati.</span><span class="sxs-lookup"><span data-stu-id="99b3a-345">The following example illustrates the limited portability that results from using culture-sensitive formatting to persist data.</span></span> <span data-ttu-id="99b3a-346">L'esempio salva una matrice di valori di data e ora in un file.</span><span class="sxs-lookup"><span data-stu-id="99b3a-346">The example saves an array of date and time values to a file.</span></span> <span data-ttu-id="99b3a-347">Questi vengono formattati usando le convenzioni delle impostazioni cultura per la lingua inglese (Stati Uniti) .</span><span class="sxs-lookup"><span data-stu-id="99b3a-347">These are formatted by using the conventions of the English (United States) culture.</span></span> <span data-ttu-id="99b3a-348">Quando l'applicazione modifica le impostazioni cultura del thread corrente in francese (Svizzera), tenta di leggere i valori salvati usando le convenzioni di formattazione delle impostazioni cultura correnti.</span><span class="sxs-lookup"><span data-stu-id="99b3a-348">After the application changes the current thread culture to French (Switzerland), it tries to read the saved values by using the formatting conventions of the current culture.</span></span> <span data-ttu-id="99b3a-349">Il tentativo di lettura di due elementi di dati genera un'eccezione [FormatException](xref:System.FormatException), quindi la matrice di date conterrà due elementi non corretti uguali a [MinValue](xref:System.DateTime.MinValue).</span><span class="sxs-lookup"><span data-stu-id="99b3a-349">The attempt to read two of the data items throws a [FormatException](xref:System.FormatException) exception, and the array of dates now contains two incorrect elements that are equal to [MinValue](xref:System.DateTime.MinValue).</span></span> 

```csharp
using System;
using System.Globalization;
using System.IO;
using System.Text;
using System.Threading;

public class Example
{
   private static string filename = @".\dates.dat";

   public static void Main()
   {
      DateTime[] dates = { new DateTime(1758, 5, 6, 21, 26, 0), 
                           new DateTime(1818, 5, 5, 7, 19, 0), 
                           new DateTime(1870, 4, 22, 23, 54, 0),  
                           new DateTime(1890, 9, 8, 6, 47, 0), 
                           new DateTime(1905, 2, 18, 15, 12, 0) }; 
      // Write the data to a file using the current culture.
      WriteData(dates);
      // Change the current culture.
      Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture("fr-CH");
      // Read the data using the current culture.
      DateTime[] newDates = ReadData();
      foreach (var newDate in newDates)
         Console.WriteLine(newDate.ToString("g"));
   }

   private static void WriteData(DateTime[] dates) 
   {
      StreamWriter sw = new StreamWriter(filename, false, Encoding.UTF8);    
      for (int ctr = 0; ctr < dates.Length; ctr++) {
         sw.Write("{0}", dates[ctr].ToString("g", CultureInfo.CurrentCulture));
         if (ctr < dates.Length - 1) sw.Write("|");   
      }      
      sw.Close();
   }

   private static DateTime[] ReadData() 
   {
      bool exceptionOccurred = false;

      // Read file contents as a single string, then split it.
      StreamReader sr = new StreamReader(filename, Encoding.UTF8);
      string output = sr.ReadToEnd();
      sr.Close();   

      string[] values = output.Split( new char[] { '|' } );
      DateTime[] newDates = new DateTime[values.Length]; 
      for (int ctr = 0; ctr < values.Length; ctr++) {
         try {
            newDates[ctr] = DateTime.Parse(values[ctr], CultureInfo.CurrentCulture);
         }
         catch (FormatException) {
            Console.WriteLine("Failed to parse {0}", values[ctr]);
            exceptionOccurred = true;
         }
      }      
      if (exceptionOccurred) Console.WriteLine();
      return newDates;
   }
}
// The example displays the following output:
//       Failed to parse 4/22/1870 11:54 PM
//       Failed to parse 2/18/1905 3:12 PM
//       
//       05.06.1758 21:26
//       05.05.1818 07:19
//       01.01.0001 00:00
//       09.08.1890 06:47
//       01.01.0001 00:00
//       01.01.0001 00:00
```

```vb
Imports System.Globalization
Imports System.IO
Imports System.Text
Imports System.Threading

Module Example
   Private filename As String = ".\dates.dat"

   Public Sub Main()
      Dim dates() As Date = { #5/6/1758 9:26PM#, #5/5/1818 7:19AM#, _ 
                              #4/22/1870 11:54PM#, #9/8/1890 6:47AM#, _ 
                              #2/18/1905 3:12PM# }
      ' Write the data to a file using the current culture.
      WriteData(dates)
      ' Change the current culture.
      Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture("fr-CH")
      ' Read the data using the current culture.
      Dim newDates() As Date = ReadData()
      For Each newDate In newDates
         Console.WriteLine(newDate.ToString("g"))
      Next
   End Sub

   Private Sub WriteData(dates() As Date)
      Dim sw As New StreamWriter(filename, False, Encoding.Utf8)    
      For ctr As Integer = 0 To dates.Length - 1
         sw.Write("{0}", dates(ctr).ToString("g", CultureInfo.CurrentCulture))
         If ctr < dates.Length - 1 Then sw.Write("|")   
      Next      
      sw.Close()
   End Sub

   Private Function ReadData() As Date()
      Dim exceptionOccurred As Boolean = False

      ' Read file contents as a single string, then split it.
      Dim sr As New StreamReader(filename, Encoding.Utf8)
      Dim output As String = sr.ReadToEnd()
      sr.Close()   

      Dim values() As String = output.Split( {"|"c } )
      Dim newDates(values.Length - 1) As Date 
      For ctr As Integer = 0 To values.Length - 1
         Try
            newDates(ctr) = DateTime.Parse(values(ctr), CultureInfo.CurrentCulture)
         Catch e As FormatException
            Console.WriteLine("Failed to parse {0}", values(ctr))
            exceptionOccurred = True
         End Try
      Next      
      If exceptionOccurred Then Console.WriteLine()
      Return newDates
   End Function
End Module
' The example displays the following output:
'       Failed to parse 4/22/1870 11:54 PM
'       Failed to parse 2/18/1905 3:12 PM
'       
'       05.06.1758 21:26
'       05.05.1818 07:19
'       01.01.0001 00:00
'       09.08.1890 06:47
'       01.01.0001 00:00
'       01.01.0001 00:00
'
```

<span data-ttu-id="99b3a-350">Tuttavia, se si sostituisce la proprietà [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture) con [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) nelle chiamate a [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) e [DateTime.Parse(String, IFormatProvider)](xref:System.DateTime.Parse(System.String,System.IFormatProvider)), i dati di data e ora persistenti vengono ripristinati come illustrato nell'output seguente.</span><span class="sxs-lookup"><span data-stu-id="99b3a-350">However, if you replace the [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture) property with [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) in the calls to [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) and [DateTime.Parse(String, IFormatProvider)](xref:System.DateTime.Parse(System.String,System.IFormatProvider)), the persisted date and time data is successfully restored, as the following output shows.</span></span>

```
// 06.05.1758 21:26
// 05.05.1818 07:19
// 22.04.1870 23:54
// 08.09.1890 06:47
// 18.02.1905 15:12
```

## <a name="see-also"></a><span data-ttu-id="99b3a-351">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99b3a-351">See also</span></span>

[<span data-ttu-id="99b3a-352">Modifica di stringhe</span><span class="sxs-lookup"><span data-stu-id="99b3a-352">Manipulating strings</span></span>](manipulating-strings.md)

