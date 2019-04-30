---
title: 'Procedura: Ripristinare i fusi orari da una risorsa incorporata'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71fc4e04c87dfa3b83eabb06361d1da94a512a5e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026536"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a><span data-ttu-id="f5d07-102">Procedura: Ripristinare i fusi orari da una risorsa incorporata</span><span class="sxs-lookup"><span data-stu-id="f5d07-102">How to: Restore time zones from an embedded resource</span></span>

<span data-ttu-id="f5d07-103">In questo argomento viene descritto come ripristinare i fusi orari che sono state salvate in un file di risorse.</span><span class="sxs-lookup"><span data-stu-id="f5d07-103">This topic describes how to restore time zones that have been saved in a resource file.</span></span> <span data-ttu-id="f5d07-104">Per informazioni e istruzioni sul salvataggio di fusi orari, vedere [come: Salvare fusi orari in una risorsa incorporata](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).</span><span class="sxs-lookup"><span data-stu-id="f5d07-104">For information and instructions about saving time zones, see [How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).</span></span>

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a><span data-ttu-id="f5d07-105">Per deserializzare un oggetto TimeZoneInfo da una risorsa incorporata</span><span class="sxs-lookup"><span data-stu-id="f5d07-105">To deserialize a TimeZoneInfo object from an embedded resource</span></span>

1. <span data-ttu-id="f5d07-106">Se il fuso orario da recuperare non è un fuso orario personalizzato, provare a crearne un'istanza utilizzando il <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="f5d07-106">If the time zone to be retrieved is not a custom time zone, try to instantiate it by using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span>

2. <span data-ttu-id="f5d07-107">Creare un'istanza di un <xref:System.Resources.ResourceManager> passando il nome completo del file di risorse incorporato e un riferimento all'assembly che contiene il file di risorse.</span><span class="sxs-lookup"><span data-stu-id="f5d07-107">Instantiate a <xref:System.Resources.ResourceManager> object by passing the fully qualified name of the embedded resource file and a reference to the assembly that contains the resource file.</span></span>

   <span data-ttu-id="f5d07-108">Se non è possibile determinare il nome completo del file di risorse incorporato, usare il [Ildasm.exe (Disassembler IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) per esaminare il manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f5d07-108">If you cannot determine the fully qualified name of the embedded resource file, use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's manifest.</span></span> <span data-ttu-id="f5d07-109">Un `.mresource` ingresso identifica la risorsa.</span><span class="sxs-lookup"><span data-stu-id="f5d07-109">An `.mresource` entry identifies the resource.</span></span> <span data-ttu-id="f5d07-110">Nell'esempio, il nome della risorsa completo è `SerializeTimeZoneData.SerializedTimeZones`.</span><span class="sxs-lookup"><span data-stu-id="f5d07-110">In the example, the resource's fully qualified name is `SerializeTimeZoneData.SerializedTimeZones`.</span></span>

   <span data-ttu-id="f5d07-111">Se il file di risorse è incorporato nello stesso assembly che contiene il codice di creazione di un'istanza di fusi orari, è possibile recuperare un riferimento a esso chiamando il `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="f5d07-111">If the resource file is embedded in the same assembly that contains the time zone instantiation code, you can retrieve a reference to it by calling the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method.</span></span>

3. <span data-ttu-id="f5d07-112">Se la chiamata ai <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> metodo ha esito negativo, o se deve essere creata un'istanza di un fuso orario personalizzato, recuperare una stringa contenente il fuso orario serializzato chiamando il <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> (metodo).</span><span class="sxs-lookup"><span data-stu-id="f5d07-112">If the call to the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method fails, or if a custom time zone is to be instantiated, retrieve a string that contains the serialized time zone by calling the <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="f5d07-113">Deserializzare i dati del fuso orario chiamando il <xref:System.TimeZoneInfo.FromSerializedString%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="f5d07-113">Deserialize the time zone data by calling the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="example"></a><span data-ttu-id="f5d07-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5d07-114">Example</span></span>

<span data-ttu-id="f5d07-115">Nell'esempio seguente viene deserializzato un <xref:System.TimeZoneInfo> oggetto archiviato in un file di risorsa XML .NET incorporato.</span><span class="sxs-lookup"><span data-stu-id="f5d07-115">The following example deserializes a <xref:System.TimeZoneInfo> object stored in an embedded .NET XML resource file.</span></span>

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

<span data-ttu-id="f5d07-116">Questo codice illustra la gestione delle eccezioni per assicurarsi che un <xref:System.TimeZoneInfo> oggetto richiesta dall'applicazione è presente.</span><span class="sxs-lookup"><span data-stu-id="f5d07-116">This code illustrates exception handling to ensure that a <xref:System.TimeZoneInfo> object required by the application is present.</span></span> <span data-ttu-id="f5d07-117">Tenta innanzitutto di creare un'istanza di un <xref:System.TimeZoneInfo> oggetto recuperandolo dal Registro di sistema utilizzando la <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="f5d07-117">It first tries to instantiate a <xref:System.TimeZoneInfo> object by retrieving it from the registry using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span> <span data-ttu-id="f5d07-118">Se il fuso orario non è possibile creare un'istanza, il codice si recupera dal file di risorsa incorporata.</span><span class="sxs-lookup"><span data-stu-id="f5d07-118">If the time zone cannot be instantiated, the code retrieves it from the embedded resource file.</span></span>

<span data-ttu-id="f5d07-119">Perché i dati per i fusi orari personalizzati (fusi orari creata un'istanza usando il <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo) non vengono archiviate nel Registro di sistema non chiama il codice il <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> per creare un'istanza del fuso orario per Palmer, Antartide.</span><span class="sxs-lookup"><span data-stu-id="f5d07-119">Because data for custom time zones (time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method) are not stored in the registry, the code does not call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> to instantiate the time zone for Palmer, Antarctica.</span></span> <span data-ttu-id="f5d07-120">Al contrario, Cerca immediatamente il file di risorse incorporate per recuperare una stringa che contiene i dati del fuso orario, prima di chiamare il <xref:System.TimeZoneInfo.FromSerializedString%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="f5d07-120">Instead, it immediately looks to the embedded resource file to retrieve a string that contains the time zone's data before it calls the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="f5d07-121">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f5d07-121">Compiling the code</span></span>

<span data-ttu-id="f5d07-122">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f5d07-122">This example requires:</span></span>

* <span data-ttu-id="f5d07-123">Aggiungere un riferimento alla DLL e Forms al progetto.</span><span class="sxs-lookup"><span data-stu-id="f5d07-123">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="f5d07-124">Che siano importati spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f5d07-124">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="f5d07-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5d07-125">See also</span></span>

- [<span data-ttu-id="f5d07-126">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="f5d07-126">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="f5d07-127">Panoramica sui fusi orari</span><span class="sxs-lookup"><span data-stu-id="f5d07-127">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="f5d07-128">Procedura: Salvare fusi orari in una risorsa incorporata</span><span class="sxs-lookup"><span data-stu-id="f5d07-128">How to: Save time zones to an embedded resource</span></span>](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
