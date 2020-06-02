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
ms.openlocfilehash: b1cece13c88b3a49c9c4c90045a07dd009d4282d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281323"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a><span data-ttu-id="ce67e-102">Procedura: ripristinare i fusi orari da una risorsa incorporata</span><span class="sxs-lookup"><span data-stu-id="ce67e-102">How to: Restore time zones from an embedded resource</span></span>

<span data-ttu-id="ce67e-103">In questo argomento viene descritto come ripristinare i fusi orari salvati in un file di risorse.</span><span class="sxs-lookup"><span data-stu-id="ce67e-103">This topic describes how to restore time zones that have been saved in a resource file.</span></span> <span data-ttu-id="ce67e-104">Per informazioni e istruzioni sul salvataggio dei fusi orari, vedere [procedura: salvare fusi orari in una risorsa incorporata](save-time-zones-to-an-embedded-resource.md).</span><span class="sxs-lookup"><span data-stu-id="ce67e-104">For information and instructions about saving time zones, see [How to: Save time zones to an embedded resource](save-time-zones-to-an-embedded-resource.md).</span></span>

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a><span data-ttu-id="ce67e-105">Per deserializzare un oggetto TimeZoneInfo da una risorsa incorporata</span><span class="sxs-lookup"><span data-stu-id="ce67e-105">To deserialize a TimeZoneInfo object from an embedded resource</span></span>

1. <span data-ttu-id="ce67e-106">Se il fuso orario da recuperare non è un fuso orario personalizzato, provare a crearne un'istanza usando il <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="ce67e-106">If the time zone to be retrieved is not a custom time zone, try to instantiate it by using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span>

2. <span data-ttu-id="ce67e-107">Creare un'istanza <xref:System.Resources.ResourceManager> di un oggetto passando il nome completo del file di risorse incorporato e un riferimento all'assembly che contiene il file di risorse.</span><span class="sxs-lookup"><span data-stu-id="ce67e-107">Instantiate a <xref:System.Resources.ResourceManager> object by passing the fully qualified name of the embedded resource file and a reference to the assembly that contains the resource file.</span></span>

   <span data-ttu-id="ce67e-108">Se non è possibile determinare il nome completo del file di risorse incorporato, utilizzare [Ildasm. exe (DISASSEMBLER il)](../../framework/tools/ildasm-exe-il-disassembler.md) per esaminare il manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ce67e-108">If you cannot determine the fully qualified name of the embedded resource file, use the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's manifest.</span></span> <span data-ttu-id="ce67e-109">Una `.mresource` voce identifica la risorsa.</span><span class="sxs-lookup"><span data-stu-id="ce67e-109">An `.mresource` entry identifies the resource.</span></span> <span data-ttu-id="ce67e-110">Nell'esempio, il nome completo della risorsa è `SerializeTimeZoneData.SerializedTimeZones` .</span><span class="sxs-lookup"><span data-stu-id="ce67e-110">In the example, the resource's fully qualified name is `SerializeTimeZoneData.SerializedTimeZones`.</span></span>

   <span data-ttu-id="ce67e-111">Se il file di risorse è incorporato nello stesso assembly contenente il codice di creazione dell'istanza del fuso orario, è possibile recuperare un riferimento a esso chiamando `static` il `Shared` Metodo (in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> .</span><span class="sxs-lookup"><span data-stu-id="ce67e-111">If the resource file is embedded in the same assembly that contains the time zone instantiation code, you can retrieve a reference to it by calling the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method.</span></span>

3. <span data-ttu-id="ce67e-112">Se la chiamata al <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> metodo ha esito negativo o se è necessario creare un'istanza di un fuso orario personalizzato, recuperare una stringa che contiene il fuso orario serializzato chiamando il <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="ce67e-112">If the call to the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method fails, or if a custom time zone is to be instantiated, retrieve a string that contains the serialized time zone by calling the <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="ce67e-113">Deserializzare i dati del fuso orario chiamando il <xref:System.TimeZoneInfo.FromSerializedString%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="ce67e-113">Deserialize the time zone data by calling the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="example"></a><span data-ttu-id="ce67e-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce67e-114">Example</span></span>

<span data-ttu-id="ce67e-115">Nell'esempio seguente viene deserializzato un <xref:System.TimeZoneInfo> oggetto archiviato in un file di risorse XML .NET incorporato.</span><span class="sxs-lookup"><span data-stu-id="ce67e-115">The following example deserializes a <xref:System.TimeZoneInfo> object stored in an embedded .NET XML resource file.</span></span>

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

<span data-ttu-id="ce67e-116">In questo codice viene illustrata la gestione delle eccezioni per assicurarsi che <xref:System.TimeZoneInfo> sia presente un oggetto necessario per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ce67e-116">This code illustrates exception handling to ensure that a <xref:System.TimeZoneInfo> object required by the application is present.</span></span> <span data-ttu-id="ce67e-117">Tenta innanzitutto di creare un'istanza <xref:System.TimeZoneInfo> di un oggetto tramite il recupero dal registro di sistema tramite il <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="ce67e-117">It first tries to instantiate a <xref:System.TimeZoneInfo> object by retrieving it from the registry using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span> <span data-ttu-id="ce67e-118">Se non è possibile creare un'istanza del fuso orario, il codice lo recupera dal file di risorse incorporato.</span><span class="sxs-lookup"><span data-stu-id="ce67e-118">If the time zone cannot be instantiated, the code retrieves it from the embedded resource file.</span></span>

<span data-ttu-id="ce67e-119">Poiché i dati per i fusi orari personalizzati (i fusi orari tramite cui viene creata un'istanza tramite il <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo) non vengono archiviati nel registro di sistema, il codice non chiama <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> per creare un'istanza del fuso orario per Palmer, Antartide.</span><span class="sxs-lookup"><span data-stu-id="ce67e-119">Because data for custom time zones (time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method) are not stored in the registry, the code does not call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> to instantiate the time zone for Palmer, Antarctica.</span></span> <span data-ttu-id="ce67e-120">Al contrario, cerca immediatamente il file di risorse incorporato per recuperare una stringa che contiene i dati del fuso orario prima di chiamare il <xref:System.TimeZoneInfo.FromSerializedString%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="ce67e-120">Instead, it immediately looks to the embedded resource file to retrieve a string that contains the time zone's data before it calls the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="ce67e-121">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ce67e-121">Compiling the code</span></span>

<span data-ttu-id="ce67e-122">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce67e-122">This example requires:</span></span>

- <span data-ttu-id="ce67e-123">Che un riferimento a System. Windows. Forms. dll e System. Core. dll venga aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="ce67e-123">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

- <span data-ttu-id="ce67e-124">Che vengano importati gli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce67e-124">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="ce67e-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce67e-125">See also</span></span>

- [<span data-ttu-id="ce67e-126">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="ce67e-126">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="ce67e-127">Panoramica sul fuso orario</span><span class="sxs-lookup"><span data-stu-id="ce67e-127">Time zone overview</span></span>](time-zone-overview.md)
- [<span data-ttu-id="ce67e-128">Procedura: salvare fusi orari in una risorsa incorporata</span><span class="sxs-lookup"><span data-stu-id="ce67e-128">How to: Save time zones to an embedded resource</span></span>](save-time-zones-to-an-embedded-resource.md)
