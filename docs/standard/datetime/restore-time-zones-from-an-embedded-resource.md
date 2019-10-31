---
title: 'Procedura: ripristinare i fusi orari da una risorsa incorporata'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
ms.openlocfilehash: cd2119d6d22f3f676b7167ed545aeb058123cfb5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122196"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a><span data-ttu-id="9aea4-102">Procedura: ripristinare i fusi orari da una risorsa incorporata</span><span class="sxs-lookup"><span data-stu-id="9aea4-102">How to: Restore time zones from an embedded resource</span></span>

<span data-ttu-id="9aea4-103">In questo argomento viene descritto come ripristinare i fusi orari salvati in un file di risorse.</span><span class="sxs-lookup"><span data-stu-id="9aea4-103">This topic describes how to restore time zones that have been saved in a resource file.</span></span> <span data-ttu-id="9aea4-104">Per informazioni e istruzioni sul salvataggio dei fusi orari, vedere [procedura: salvare fusi orari in una risorsa incorporata](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).</span><span class="sxs-lookup"><span data-stu-id="9aea4-104">For information and instructions about saving time zones, see [How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).</span></span>

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a><span data-ttu-id="9aea4-105">Per deserializzare un oggetto TimeZoneInfo da una risorsa incorporata</span><span class="sxs-lookup"><span data-stu-id="9aea4-105">To deserialize a TimeZoneInfo object from an embedded resource</span></span>

1. <span data-ttu-id="9aea4-106">Se il fuso orario da recuperare non è un fuso orario personalizzato, provare a crearne un'istanza usando il metodo <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>.</span><span class="sxs-lookup"><span data-stu-id="9aea4-106">If the time zone to be retrieved is not a custom time zone, try to instantiate it by using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span>

2. <span data-ttu-id="9aea4-107">Creare un'istanza di un oggetto <xref:System.Resources.ResourceManager> passando il nome completo del file di risorse incorporato e un riferimento all'assembly che contiene il file di risorse.</span><span class="sxs-lookup"><span data-stu-id="9aea4-107">Instantiate a <xref:System.Resources.ResourceManager> object by passing the fully qualified name of the embedded resource file and a reference to the assembly that contains the resource file.</span></span>

   <span data-ttu-id="9aea4-108">Se non è possibile determinare il nome completo del file di risorse incorporato, utilizzare [Ildasm. exe (DISASSEMBLER il)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) per esaminare il manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="9aea4-108">If you cannot determine the fully qualified name of the embedded resource file, use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's manifest.</span></span> <span data-ttu-id="9aea4-109">Una voce di `.mresource` identifica la risorsa.</span><span class="sxs-lookup"><span data-stu-id="9aea4-109">An `.mresource` entry identifies the resource.</span></span> <span data-ttu-id="9aea4-110">Nell'esempio, il nome completo della risorsa è `SerializeTimeZoneData.SerializedTimeZones`.</span><span class="sxs-lookup"><span data-stu-id="9aea4-110">In the example, the resource's fully qualified name is `SerializeTimeZoneData.SerializedTimeZones`.</span></span>

   <span data-ttu-id="9aea4-111">Se il file di risorse è incorporato nello stesso assembly contenente il codice di creazione dell'istanza del fuso orario, è possibile recuperare un riferimento a esso chiamando il metodo `static` (`Shared` Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A>.</span><span class="sxs-lookup"><span data-stu-id="9aea4-111">If the resource file is embedded in the same assembly that contains the time zone instantiation code, you can retrieve a reference to it by calling the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method.</span></span>

3. <span data-ttu-id="9aea4-112">Se la chiamata al metodo <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> ha esito negativo o se è necessario creare un'istanza di un fuso orario personalizzato, recuperare una stringa che contiene il fuso orario serializzato chiamando il metodo <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9aea4-112">If the call to the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method fails, or if a custom time zone is to be instantiated, retrieve a string that contains the serialized time zone by calling the <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="9aea4-113">Deserializzare i dati del fuso orario chiamando il metodo <xref:System.TimeZoneInfo.FromSerializedString%2A>.</span><span class="sxs-lookup"><span data-stu-id="9aea4-113">Deserialize the time zone data by calling the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="example"></a><span data-ttu-id="9aea4-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="9aea4-114">Example</span></span>

<span data-ttu-id="9aea4-115">Nell'esempio seguente viene deserializzato un oggetto <xref:System.TimeZoneInfo> archiviato in un file di risorse XML .NET incorporato.</span><span class="sxs-lookup"><span data-stu-id="9aea4-115">The following example deserializes a <xref:System.TimeZoneInfo> object stored in an embedded .NET XML resource file.</span></span>

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

<span data-ttu-id="9aea4-116">In questo codice viene illustrata la gestione delle eccezioni per assicurarsi che sia presente un <xref:System.TimeZoneInfo> oggetto richiesto dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9aea4-116">This code illustrates exception handling to ensure that a <xref:System.TimeZoneInfo> object required by the application is present.</span></span> <span data-ttu-id="9aea4-117">Tenta innanzitutto di creare un'istanza di un oggetto <xref:System.TimeZoneInfo> tramite il recupero dal registro di sistema tramite il metodo <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>.</span><span class="sxs-lookup"><span data-stu-id="9aea4-117">It first tries to instantiate a <xref:System.TimeZoneInfo> object by retrieving it from the registry using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span> <span data-ttu-id="9aea4-118">Se non è possibile creare un'istanza del fuso orario, il codice lo recupera dal file di risorse incorporato.</span><span class="sxs-lookup"><span data-stu-id="9aea4-118">If the time zone cannot be instantiated, the code retrieves it from the embedded resource file.</span></span>

<span data-ttu-id="9aea4-119">Poiché i dati per i fusi orari personalizzati (fusi orari creati con il metodo <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>) non vengono archiviati nel registro di sistema, il codice non chiama il <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> per creare un'istanza del fuso orario per Palmer, Antartide.</span><span class="sxs-lookup"><span data-stu-id="9aea4-119">Because data for custom time zones (time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method) are not stored in the registry, the code does not call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> to instantiate the time zone for Palmer, Antarctica.</span></span> <span data-ttu-id="9aea4-120">Al contrario, cerca immediatamente il file di risorse incorporato per recuperare una stringa che contiene i dati del fuso orario prima di chiamare il metodo <xref:System.TimeZoneInfo.FromSerializedString%2A>.</span><span class="sxs-lookup"><span data-stu-id="9aea4-120">Instead, it immediately looks to the embedded resource file to retrieve a string that contains the time zone's data before it calls the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="9aea4-121">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="9aea4-121">Compiling the code</span></span>

<span data-ttu-id="9aea4-122">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9aea4-122">This example requires:</span></span>

- <span data-ttu-id="9aea4-123">Che un riferimento a System. Windows. Forms. dll e System. Core. dll venga aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="9aea4-123">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

- <span data-ttu-id="9aea4-124">Che vengano importati gli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9aea4-124">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="9aea4-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9aea4-125">See also</span></span>

- [<span data-ttu-id="9aea4-126">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="9aea4-126">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="9aea4-127">Panoramica sui fusi orari</span><span class="sxs-lookup"><span data-stu-id="9aea4-127">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="9aea4-128">Procedura: Salvare fusi orari in una risorsa incorporata</span><span class="sxs-lookup"><span data-stu-id="9aea4-128">How to: Save time zones to an embedded resource</span></span>](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
