---
title: Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura nelle raccolte
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CaseInsensitiveComparer class, using
- CollectionsUtil.CreateCaseInsensitiveHashtable method
- culture-insensitive string operations, collections
- collections [.NET Framework], culture-insensitive string operations
- CaseInsensitiveHashCodeProvider class, using
- ArrayList.Sort method
- SortedList class, culture-insensitive string operations
- culture parameter
ms.assetid: 5cdc9396-a64b-4615-a1cd-b605db4c5983
ms.openlocfilehash: 13a9f4896a37be4297f2a1a11435b85ade381c66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74353665"
---
# <a name="performing-culture-insensitive-string-operations-in-collections"></a><span data-ttu-id="6c58b-102">Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura nelle raccolte</span><span class="sxs-lookup"><span data-stu-id="6c58b-102">Performing Culture-Insensitive String Operations in Collections</span></span>

<span data-ttu-id="6c58b-103">Nello spazio dei nomi <xref:System.Collections> sono disponibili classi e membri che per impostazione predefinita forniscono un comportamento dipendente dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="6c58b-103">There are classes and members in the <xref:System.Collections> namespace that provide culture-sensitive behavior by default.</span></span> <span data-ttu-id="6c58b-104">I costruttori senza parametri per le classi <xref:System.Collections.CaseInsensitiveComparer> e <xref:System.Collections.CaseInsensitiveHashCodeProvider> inizializzano una nuova istanza tramite la proprietà <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6c58b-104">The parameterless constructors for the <xref:System.Collections.CaseInsensitiveComparer> and <xref:System.Collections.CaseInsensitiveHashCodeProvider> classes initialize a new instance using the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="6c58b-105">Per impostazione predefinita, tutti gli overload del metodo <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> creano una nuova istanza della classe <xref:System.Collections.Hashtable> tramite la proprietà `Thread.CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="6c58b-105">All overloads of the <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> method create a new instance of the <xref:System.Collections.Hashtable> class using the `Thread.CurrentCulture` property by default.</span></span> <span data-ttu-id="6c58b-106">Per impostazione predefinita, gli overload del metodo <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> consentono di eseguire ordinamenti dipendenti dalle impostazioni cultura tramite `Thread.CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="6c58b-106">Overloads of the <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> method perform culture-sensitive sorts by default using `Thread.CurrentCulture`.</span></span> <span data-ttu-id="6c58b-107">Ordinamento e ricerca in un <xref:System.Collections.SortedList> possono essere influenzati dal `Thread.CurrentCulture` quando vengono usate stringhe come chiavi.</span><span class="sxs-lookup"><span data-stu-id="6c58b-107">Sorting and lookup in a <xref:System.Collections.SortedList> can be affected by `Thread.CurrentCulture` when strings are used as the keys.</span></span> <span data-ttu-id="6c58b-108">Per ottenere risultati indipendenti dalle impostazioni cultura da queste classi e da questi metodi dello spazio dei nomi `Collections`, attenersi ai consigli sull'utilizzo forniti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="6c58b-108">Follow the usage recommendations provided in this section to obtain culture-insensitive results from these classes and methods in the `Collections` namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="6c58b-109">Il <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> passaggio a un metodo di confronto esegue un confronto indipendente dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="6c58b-109">Passing <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> to a comparison method does perform a culture-insensitive comparison.</span></span> <span data-ttu-id="6c58b-110">Non viene tuttavia eseguito un confronto non linguistico, ad esempio per percorsi di file, chiavi del Registro di sistema e variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="6c58b-110">However, it does not cause a non-linguistic comparison, for example, for file paths, registry keys, and environment variables.</span></span> <span data-ttu-id="6c58b-111">e non sono supportate le decisioni relative alla sicurezza basate sul risultato del confronto.</span><span class="sxs-lookup"><span data-stu-id="6c58b-111">Neither does it support security decisions based on the comparison result.</span></span> <span data-ttu-id="6c58b-112">Per un confronto non linguistico o per il supporto delle decisioni relative alla sicurezza basate sul risultato, l'applicazione deve utilizzare un metodo di confronto che accetti un valore <xref:System.StringComparison>.</span><span class="sxs-lookup"><span data-stu-id="6c58b-112">For a non-linguistic comparison or support for result-based security decisions, the application should use a comparison method that accepts a <xref:System.StringComparison> value.</span></span> <span data-ttu-id="6c58b-113">L'applicazione deve quindi passare <xref:System.StringComparison>.</span><span class="sxs-lookup"><span data-stu-id="6c58b-113">The application should then pass <xref:System.StringComparison>.</span></span>

## <a name="using-the-caseinsensitivecomparer-and-caseinsensitivehashcodeprovider-classes"></a><span data-ttu-id="6c58b-114">Uso delle classi CaseInsensitiveComparer e CaseInsensitiveHashCodeProvider</span><span class="sxs-lookup"><span data-stu-id="6c58b-114">Using the CaseInsensitiveComparer and CaseInsensitiveHashCodeProvider Classes</span></span>

<span data-ttu-id="6c58b-115">I costruttori senza parametri per `CaseInsensitiveHashCodeProvider` e `CaseInsensitiveComparer` inizializzano una nuova istanza della classe tramite `Thread.CurrentCulture`, determinando così un comportamento dipendente dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="6c58b-115">The parameterless constructors for `CaseInsensitiveHashCodeProvider` and `CaseInsensitiveComparer` initialize a new instance of the class using the `Thread.CurrentCulture`, resulting in culture-sensitive behavior.</span></span> <span data-ttu-id="6c58b-116">Nell'esempio di codice seguente viene illustrato il costruttore per un oggetto `Hashtable` dipendente dalle impostazioni cultura in quanto usa i costruttori senza parametri per `CaseInsensitiveHashCodeProvider` e `CaseInsensitiveComparer`.</span><span class="sxs-lookup"><span data-stu-id="6c58b-116">The following code example demonstrates the constructor for a `Hashtable` that is culture-sensitive because it uses the parameterless constructors for `CaseInsensitiveHashCodeProvider` and `CaseInsensitiveComparer`.</span></span>

```vb
internalHashtable = New Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default)
```

```csharp
internalHashtable = new Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default);
```

<span data-ttu-id="6c58b-117">Per creare un oggetto `Hashtable` non basato sulle impostazioni di cultura usando le classi `CaseInsensitiveComparer` e `CaseInsensitiveHashCodeProvider`, inizializzare nuove istanze di queste classi utilizzando costruttori che accettano un parametro `culture`.</span><span class="sxs-lookup"><span data-stu-id="6c58b-117">If you want to create a culture-insensitive `Hashtable` using the `CaseInsensitiveComparer` and `CaseInsensitiveHashCodeProvider` classes, initialize new instances of these classes using the constructors that accept a `culture` parameter.</span></span> <span data-ttu-id="6c58b-118">Per il parametro `culture` specificare <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6c58b-118">For the `culture` parameter, specify <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6c58b-119">Nell'esempio di codice seguente viene illustrato il costruttore per un oggetto `Hashtable` indipendente dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="6c58b-119">The following code example demonstrates the constructor for a culture-insensitive `Hashtable`.</span></span>

```vb
internalHashtable = New Hashtable(New
    CaseInsensitiveHashCodeProvider(CultureInfo.InvariantCulture),
    New CaseInsensitiveComparer(CultureInfo.InvariantCulture))
```

```csharp
internalHashtable = new Hashtable(new CaseInsensitiveHashCodeProvider
    (CultureInfo.InvariantCulture),
    new CaseInsensitiveComparer(CultureInfo.InvariantCulture));
```

## <a name="using-the-collectionsutilcreatecaseinsensitivehashtable-method"></a><span data-ttu-id="6c58b-120">Utilizzo del metodo CollectionsUtil.CreateCaseInsensitiveHashtable</span><span class="sxs-lookup"><span data-stu-id="6c58b-120">Using the CollectionsUtil.CreateCaseInsensitiveHashTable Method</span></span>

<span data-ttu-id="6c58b-121">Il metodo `CollectionsUtil.CreateCaseInsensitiveHashTable` rappresenta un rapido meccanismo per creare una nuova istanza della classe `Hashtable` in cui viene ignorato l'uso di maiuscole e minuscole nelle stringhe.</span><span class="sxs-lookup"><span data-stu-id="6c58b-121">The `CollectionsUtil.CreateCaseInsensitiveHashTable` method is a useful shortcut for creating a new instance of the `Hashtable` class that ignores the case of strings.</span></span> <span data-ttu-id="6c58b-122">Tutti gli overload del metodo `CollectionsUtil.CreateCaseInsensitiveHashTable` sono tuttavia dipendenti dalle impostazioni cultura in quanto utilizzano la proprietà `Thread.CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="6c58b-122">However, all overloads of the `CollectionsUtil.CreateCaseInsensitiveHashTable` method are culture-sensitive because they use the `Thread.CurrentCulture` property.</span></span> <span data-ttu-id="6c58b-123">Con questo metodo non è possibile creare un oggetto `Hashtable` indipendente dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="6c58b-123">You cannot create a culture-insensitive `Hashtable` using this method.</span></span> <span data-ttu-id="6c58b-124">Per creare un oggetto `Hashtable` indipendente dalle impostazioni cultura, usare il costruttore di `Hashtable`che accetta un parametro `culture`.</span><span class="sxs-lookup"><span data-stu-id="6c58b-124">To create a culture-insensitive `Hashtable`, use the `Hashtable` constructor that accepts a `culture` parameter.</span></span> <span data-ttu-id="6c58b-125">Per il parametro `culture` specificare `CultureInfo.InvariantCulture`.</span><span class="sxs-lookup"><span data-stu-id="6c58b-125">For the `culture` parameter, specify `CultureInfo.InvariantCulture`.</span></span> <span data-ttu-id="6c58b-126">Nell'esempio di codice seguente viene illustrato il costruttore per un oggetto `Hashtable` indipendente dalle impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="6c58b-126">The following code example demonstrates the constructor for a culture-insensitive `Hashtable`.</span></span>

```vb
internalHashtable = New Hashtable(New
    CaseInsensitiveHashCodeProvider(CultureInfo.InvariantCulture),
    New CaseInsensitiveComparer(CultureInfo.InvariantCulture))
```

```csharp
internalHashtable = new Hashtable(new CaseInsensitiveHashCodeProvider
    (CultureInfo.InvariantCulture),
    new CaseInsensitiveComparer(CultureInfo.InvariantCulture));
```

<a name="cpconperformingculture-insensitivestringoperationsincollectionsanchor1"></a>

## <a name="using-the-sortedlist-class"></a><span data-ttu-id="6c58b-127">Utilizzo della classe SortedList</span><span class="sxs-lookup"><span data-stu-id="6c58b-127">Using the SortedList Class</span></span>

<span data-ttu-id="6c58b-128">Un oggetto `SortedList` rappresenta una raccolta di coppie chiave-valore ordinate in base alle chiavi e a cui è possibile accedere in base alla chiave e all'indice.</span><span class="sxs-lookup"><span data-stu-id="6c58b-128">A `SortedList` represents a collection of key-and-value pairs that are sorted by the keys and are accessible by key and by index.</span></span> <span data-ttu-id="6c58b-129">Quando si utilizza un oggetto `SortedList` in cui le chiavi sono costituite da stringhe, è possibile che la proprietà `Thread.CurrentCulture` influisca sull'ordinamento e sulla ricerca.</span><span class="sxs-lookup"><span data-stu-id="6c58b-129">When you use a `SortedList` where strings are the keys, the sorting and lookup can be affected by the `Thread.CurrentCulture` property.</span></span> <span data-ttu-id="6c58b-130">Per ottenere un comportamento indipendente dalle impostazioni cultura da un oggetto `SortedList`, creare un oggetto `SortedList` con uno dei costruttori che accetta un parametro `comparer`.</span><span class="sxs-lookup"><span data-stu-id="6c58b-130">To obtain culture-insensitive behavior from a `SortedList`, create a `SortedList` using one of the constructors that accepts a `comparer` parameter.</span></span> <span data-ttu-id="6c58b-131">Il parametro `comparer` specifica l'implementazione di <xref:System.Collections.IComparer> da usare quando si confrontano le chiavi.</span><span class="sxs-lookup"><span data-stu-id="6c58b-131">The `comparer` parameter specifies the <xref:System.Collections.IComparer> implementation to use when comparing keys.</span></span> <span data-ttu-id="6c58b-132">Per il parametro, specificare una classe di operatori di confronto personalizzata che usi `CultureInfo.InvariantCulture` per il confronto delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="6c58b-132">For the parameter, specify a custom comparer class that uses `CultureInfo.InvariantCulture` to compare keys.</span></span> <span data-ttu-id="6c58b-133">Nell'esempio seguente viene illustrata una classe personalizzata di operatori di confronto indipendenti dalle impostazioni cultura che è possibile specificare come parametro `comparer` per un costruttore di `SortedList`.</span><span class="sxs-lookup"><span data-stu-id="6c58b-133">The following example illustrates a custom culture-insensitive comparer class that you can specify as the `comparer` parameter to a `SortedList` constructor.</span></span>

```vb
Imports System.Collections
Imports System.Globalization

Friend Class InvariantComparer
    Implements IComparer
    Private m_compareInfo As CompareInfo
    Friend Shared [Default] As New InvariantComparer()

    Friend Sub New()
        m_compareInfo = CultureInfo.InvariantCulture.CompareInfo
    End Sub

    Public Function Compare(a As Object, b As Object) As Integer _
            Implements IComparer.Compare
        Dim sa As String = CType(a, String)
        Dim sb As String = CType(b, String)
        If Not (sa Is Nothing) And Not (sb Is Nothing) Then
            Return m_compareInfo.Compare(sa, sb)
        Else
            Return Comparer.Default.Compare(a, b)
        End If
    End Function
End Class
```

```csharp
using System;
using System.Collections;
using System.Globalization;

internal class InvariantComparer : IComparer
{
    private CompareInfo m_compareInfo;
    internal static readonly InvariantComparer Default = new
        InvariantComparer();

    internal InvariantComparer()
    {
        m_compareInfo = CultureInfo.InvariantCulture.CompareInfo;
    }

    public int Compare(Object a, Object b)
    {
        String sa = a as String;
        String sb = b as String;
        if (sa != null && sb != null)
            return m_compareInfo.Compare(sa, sb);
        else
            return Comparer.Default.Compare(a,b);
    }
}
```

<span data-ttu-id="6c58b-134">In generale, se si utilizza un oggetto `SortedList` nelle stringhe senza specificare un operatore di confronto invariabile personalizzato, è possibile che l'elenco venga invalidato da una modifica apportata a `Thread.CurrentCulture` dopo che vi sono state inserite voci.</span><span class="sxs-lookup"><span data-stu-id="6c58b-134">In general, if you use a `SortedList` on strings without specifying a custom invariant comparer, a change to `Thread.CurrentCulture` after the list has been populated can invalidate the list.</span></span>

## <a name="using-the-arraylistsort-method"></a><span data-ttu-id="6c58b-135">Utilizzo del metodo ArrayList.Sort</span><span class="sxs-lookup"><span data-stu-id="6c58b-135">Using the ArrayList.Sort Method</span></span>

<span data-ttu-id="6c58b-136">Per impostazione predefinita, gli overload del metodo `ArrayList.Sort` consentono di eseguire ordinamenti dipendenti dalle impostazioni cultura tramite la proprietà `Thread.CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="6c58b-136">Overloads of the `ArrayList.Sort` method perform culture-sensitive sorts by default using the `Thread.CurrentCulture` property.</span></span> <span data-ttu-id="6c58b-137">I risultati possono variare in base alle impostazioni cultura, a causa di diversi criteri di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="6c58b-137">Results can vary by culture due to different sort orders.</span></span> <span data-ttu-id="6c58b-138">Per eliminare il comportamento dipendente dalle impostazioni cultura, utilizzare gli overload del metodo che accettano un'implementazione di `IComparer`.</span><span class="sxs-lookup"><span data-stu-id="6c58b-138">To eliminate culture-sensitive behavior, use the overloads of this method that accept an `IComparer` implementation.</span></span> <span data-ttu-id="6c58b-139">Per il parametro `comparer`, specificare una classe di operatori di confronto invariabili personalizzati che usi `CultureInfo.InvariantCulture`.</span><span class="sxs-lookup"><span data-stu-id="6c58b-139">For the `comparer` parameter, specify a custom invariant comparer class that uses `CultureInfo.InvariantCulture`.</span></span> <span data-ttu-id="6c58b-140">Per un esempio di classe di questo tipo, vedere l'argomento [Utilizzo della classe SortedList](#cpconperformingculture-insensitivestringoperationsincollectionsanchor1).</span><span class="sxs-lookup"><span data-stu-id="6c58b-140">An example of a custom invariant comparer class is provided in the [Using the SortedList Class](#cpconperformingculture-insensitivestringoperationsincollectionsanchor1) topic.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c58b-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c58b-141">See also</span></span>

- <xref:System.Collections.CaseInsensitiveComparer>
- <xref:System.Collections.CaseInsensitiveHashCodeProvider>
- <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType>
- <xref:System.Collections.SortedList>
- <xref:System.Collections.Hashtable>
- <xref:System.Collections.IComparer>
- [<span data-ttu-id="6c58b-142">Esecuzione di operazioni sulle stringhe indipendenti dalle impostazioni cultura</span><span class="sxs-lookup"><span data-stu-id="6c58b-142">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
- <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType>
