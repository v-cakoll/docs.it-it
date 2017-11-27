---
title: 'Procedura: enumerare i fusi orari presenti in un computer'
ms.custom: 
ms.date: 04/10/2017
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
- time zones [.NET Framework], enumerating
- enumerating time zones [.NET Framework]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f77afc8a0f2e6c110f4dc037c12ecc8b06908e60
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a><span data-ttu-id="7e19a-102">Procedura: enumerare i fusi orari presenti in un computer</span><span class="sxs-lookup"><span data-stu-id="7e19a-102">How to: Enumerate time zones present on a computer</span></span>

<span data-ttu-id="7e19a-103">Per poter usare correttamente un determinato fuso orario è necessario che nel sistema siano disponibili le informazioni sul fuso orario.</span><span class="sxs-lookup"><span data-stu-id="7e19a-103">Successfully working with a designated time zone requires that information about that time zone be available to the system.</span></span> <span data-ttu-id="7e19a-104">I sistemi operativi Windows XP e Windows Vista archiviare queste informazioni nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="7e19a-104">The Windows XP and Windows Vista operating systems store this information in the registry.</span></span> <span data-ttu-id="7e19a-105">Sebbene nel mondo esistano molti fusi orari, le informazioni presenti nel Registro di sistema sono relative solo a una parte di essi.</span><span class="sxs-lookup"><span data-stu-id="7e19a-105">However, although the total number of time zones that exist throughout the world is large, the registry contains information about only a subset of them.</span></span> <span data-ttu-id="7e19a-106">Inoltre, il Registro di sistema è una struttura dinamica il cui contenuto è soggetto a modifiche intenzionali e accidentali.</span><span class="sxs-lookup"><span data-stu-id="7e19a-106">In addition, the registry itself is a dynamic structure whose contents are subject to both deliberate and accidental change.</span></span> <span data-ttu-id="7e19a-107">Di conseguenza, un'applicazione non può sempre presupporre che un determinato fuso orario sia definito e disponibile in un sistema.</span><span class="sxs-lookup"><span data-stu-id="7e19a-107">As a result, an application cannot always assume that a particular time zone is defined and available on a system.</span></span> <span data-ttu-id="7e19a-108">Il primo passaggio per molte applicazioni che si basano sulle informazioni del fuso orario è determinare se i fusi orari richiesti sono disponibili nel sistema locale o offrire all'utente un elenco di fusi orari da selezionare.</span><span class="sxs-lookup"><span data-stu-id="7e19a-108">The first step for many applications that use time zone information applications is to determine whether required time zones are available on the local system, or to give the user a list of time zones from which to select.</span></span> <span data-ttu-id="7e19a-109">A tale scopo, è necessario che un'applicazione sia in grado di enumerare i fusi orari definiti in un sistema locale.</span><span class="sxs-lookup"><span data-stu-id="7e19a-109">This requires that an application enumerate the time zones defined on a local system.</span></span>

> [!NOTE]
> <span data-ttu-id="7e19a-110">Se un'applicazione si basa sulla presenza di un particolare fuso orario non può essere definita in un sistema locale, l'applicazione può garantire la sua presenza da serializzare e deserializzare le informazioni sul fuso orario.</span><span class="sxs-lookup"><span data-stu-id="7e19a-110">If an application relies on the presence of a particular time zone that may not be defined on a local system, the application can ensure its presence by serializing and deserializing information about the time zone.</span></span> <span data-ttu-id="7e19a-111">Il fuso orario possono aggiungere a un controllo elenco in modo che l'utente dell'applicazione è possibile selezionarla.</span><span class="sxs-lookup"><span data-stu-id="7e19a-111">The time zone can then be added to a list control so that the application user can select it.</span></span> <span data-ttu-id="7e19a-112">Per informazioni dettagliate, vedere [procedura: salvare fusi orari per una risorsa incorporata](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) e [procedura: ripristinare fusi orari da una risorsa incorporata](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).</span><span class="sxs-lookup"><span data-stu-id="7e19a-112">For details, see [How to: Save Time Zones to an Embedded Resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) and [How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).</span></span>

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a><span data-ttu-id="7e19a-113">Per enumerare i fusi orari presenti nel sistema locale</span><span class="sxs-lookup"><span data-stu-id="7e19a-113">To enumerate the time zones present on the local system</span></span>

1. <span data-ttu-id="7e19a-114">Chiamare il metodo <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7e19a-114">Call the <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7e19a-115">Il metodo restituisce un oggetto generico <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> insieme di <xref:System.TimeZoneInfo> oggetti.</span><span class="sxs-lookup"><span data-stu-id="7e19a-115">The method returns a generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects.</span></span> <span data-ttu-id="7e19a-116">Le voci nella raccolta vengono ordinate i <xref:System.TimeZoneInfo.DisplayName%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="7e19a-116">The entries in the collection are sorted by their <xref:System.TimeZoneInfo.DisplayName%2A> property.</span></span> <span data-ttu-id="7e19a-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7e19a-117">For example:</span></span>

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. <span data-ttu-id="7e19a-118">Enumerare i singoli <xref:System.TimeZoneInfo> oggetti nella raccolta utilizzando un `foreach` ciclo (in c#) o un `For Each`...`Next`</span><span class="sxs-lookup"><span data-stu-id="7e19a-118">Enumerate the individual <xref:System.TimeZoneInfo> objects in the collection by using a `foreach` loop (in C#) or a `For Each`…`Next`</span></span> <span data-ttu-id="7e19a-119">ciclo (in Visual Basic) ed eseguire tutte le elaborazioni necessarie su ogni oggetto.</span><span class="sxs-lookup"><span data-stu-id="7e19a-119">loop (in Visual Basic), and perform any necessary processing on each object.</span></span> <span data-ttu-id="7e19a-120">Ad esempio, il codice seguente enumera il <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> insieme di <xref:System.TimeZoneInfo> degli oggetti restituiti nel passaggio 1 e viene elencato il nome visualizzato di ogni fuso orario nella console.</span><span class="sxs-lookup"><span data-stu-id="7e19a-120">For example, the following code enumerates the <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects returned in step 1 and lists the display name of each time zone on the console.</span></span>

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a><span data-ttu-id="7e19a-121">Per presentare all'utente un elenco di fusi orari presenti nel sistema locale</span><span class="sxs-lookup"><span data-stu-id="7e19a-121">To present the user with a list of time zones present on the local system</span></span>

1. <span data-ttu-id="7e19a-122">Chiamare il metodo <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7e19a-122">Call the <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7e19a-123">Il metodo restituisce un oggetto generico <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> insieme di <xref:System.TimeZoneInfo> oggetti.</span><span class="sxs-lookup"><span data-stu-id="7e19a-123">The method returns a generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects.</span></span>

2. <span data-ttu-id="7e19a-124">Assegnare la raccolta restituita nel passaggio 1 per il `DataSource` proprietà di un Windows Form o ASP.NET controllo elenco.</span><span class="sxs-lookup"><span data-stu-id="7e19a-124">Assign the collection returned in step 1 to the `DataSource` property of a Windows forms or ASP.NET list control.</span></span>

3. <span data-ttu-id="7e19a-125">Recuperare il <xref:System.TimeZoneInfo> oggetto che l'utente ha selezionato.</span><span class="sxs-lookup"><span data-stu-id="7e19a-125">Retrieve the <xref:System.TimeZoneInfo> object that the user has selected.</span></span>

<span data-ttu-id="7e19a-126">Nell'esempio viene illustrato questo concetto per un'applicazione Windows.</span><span class="sxs-lookup"><span data-stu-id="7e19a-126">The example provides an illustration for a Windows application.</span></span>

## <a name="example"></a><span data-ttu-id="7e19a-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="7e19a-127">Example</span></span>

<span data-ttu-id="7e19a-128">Nell'esempio viene avviata un'applicazione Windows che consente di visualizzare i fusi orari definiti in un sistema in una casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="7e19a-128">The example starts a Windows application that displays the time zones defined on a system in a list box.</span></span> <span data-ttu-id="7e19a-129">Nell'esempio viene quindi visualizzata una finestra di dialogo che contiene il valore del <xref:System.TimeZoneInfo.DisplayName%2A> proprietà dell'oggetto fuso orario selezionato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="7e19a-129">The example then displays a dialog box that contains the value of the <xref:System.TimeZoneInfo.DisplayName%2A> property of the time zone object selected by the user.</span></span>

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

<span data-ttu-id="7e19a-130">Più controlli di elenco (ad esempio il <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> o <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> controllo) consentono di assegnare una raccolta di variabili oggetto per loro `DataSource` , purché tale raccolta implementa proprietà il <xref:System.Collections.IEnumerable> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7e19a-130">Most list controls (such as the <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> or <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> control) allow you to assign a collection of object variables to their `DataSource` property as long as that collection implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="7e19a-131">(Generico <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> eseguita dalla classe.) Per visualizzare un singolo oggetto nella raccolta, il controllo chiama tale oggetto `ToString` metodo per estrarre la stringa utilizzata per rappresentare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7e19a-131">(The generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> class does this.) To display an individual object in the collection, the control calls that object's `ToString` method to extract the string that is used to represent the object.</span></span> <span data-ttu-id="7e19a-132">In caso di <xref:System.TimeZoneInfo> oggetti, il `ToString` metodo restituisce il <xref:System.TimeZoneInfo> nome visualizzato dell'oggetto (il valore della relativa <xref:System.TimeZoneInfo.DisplayName%2A> proprietà).</span><span class="sxs-lookup"><span data-stu-id="7e19a-132">In the case of <xref:System.TimeZoneInfo> objects, the `ToString` method returns the <xref:System.TimeZoneInfo> object's display name (the value of its <xref:System.TimeZoneInfo.DisplayName%2A> property).</span></span>

> [!NOTE]
> <span data-ttu-id="7e19a-133">Poiché i controlli elenco chiamano un oggetto `ToString` (metodo), è possibile assegnare una raccolta di <xref:System.TimeZoneInfo> oggetti per il controllo, che il controllo Visualizza un nome significativo per ogni oggetto e recuperare il <xref:System.TimeZoneInfo> oggetto che l'utente ha selezionato.</span><span class="sxs-lookup"><span data-stu-id="7e19a-133">Because list controls call an object's `ToString` method, you can assign a collection of <xref:System.TimeZoneInfo> objects to the control, have the control display a meaningful name for each object, and retrieve the <xref:System.TimeZoneInfo> object that the user has selected.</span></span> <span data-ttu-id="7e19a-134">Questo elimina la necessità di estrarre una stringa per ogni oggetto nella raccolta, la stringa assegnata a una raccolta che a sua volta viene assegnata al controllo `DataSource` proprietà, recuperare la stringa di cui l'utente ha selezionato e quindi questa stringa viene utilizzata per estrarre l'oggetto che descrive.</span><span class="sxs-lookup"><span data-stu-id="7e19a-134">This eliminates the need to extract a string for each object in the collection, assign the string to a collection that is in turn assigned to the control's `DataSource` property, retrieve the string the user has selected, and then use this string to extract the object that it describes.</span></span> 

## <a name="compiling-the-code"></a><span data-ttu-id="7e19a-135">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7e19a-135">Compiling the code</span></span>

<span data-ttu-id="7e19a-136">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e19a-136">This example requires:</span></span>

* <span data-ttu-id="7e19a-137">Un riferimento a System.Core.dll essere aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="7e19a-137">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="7e19a-138">Che importati spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e19a-138">That the following namespaces be imported:</span></span>

  <span data-ttu-id="7e19a-139"><xref:System>(in codice c#)</span><span class="sxs-lookup"><span data-stu-id="7e19a-139"><xref:System> (in C# code)</span></span>

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a><span data-ttu-id="7e19a-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e19a-140">See also</span></span>

<span data-ttu-id="7e19a-141">[Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
[procedura: salvare fusi orari per una risorsa incorporata](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
[procedura: ripristinare fusi orari da una risorsa incorporata](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span><span class="sxs-lookup"><span data-stu-id="7e19a-141">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
[How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span></span>
