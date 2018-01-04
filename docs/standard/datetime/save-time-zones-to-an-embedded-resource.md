---
title: 'Procedura: salvare fusi orari per una risorsa incorporata'
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
- time zones [.NET Framework], saving
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 93dfc62df1c1d68e09a3734402924bbac1a074cb
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a><span data-ttu-id="bde2e-102">Procedura: salvare fusi orari per una risorsa incorporata</span><span class="sxs-lookup"><span data-stu-id="bde2e-102">How to: Save time zones to an embedded resource</span></span>

<span data-ttu-id="bde2e-103">Un'applicazione di fuso orario spesso richiede la presenza di un particolare fuso orario.</span><span class="sxs-lookup"><span data-stu-id="bde2e-103">A time zone-aware application often requires the presence of a particular time zone.</span></span> <span data-ttu-id="bde2e-104">Tuttavia, poiché la disponibilità dei singoli <xref:System.TimeZoneInfo> oggetti dipende dalle informazioni archiviate nel Registro di sistema locale, anche fusi orari generalmente disponibili potrebbe essere assente.</span><span class="sxs-lookup"><span data-stu-id="bde2e-104">However, because the availability of individual <xref:System.TimeZoneInfo> objects depends on information stored in the local system's registry, even customarily available time zones may be absent.</span></span> <span data-ttu-id="bde2e-105">Inoltre, viene creata un'istanza di informazioni sui fusi orari personalizzati utilizzando il <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> (metodo) non è archiviata con altre informazioni sul fuso orario nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="bde2e-105">In addition, information about custom time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method is not stored with other time zone information in the registry.</span></span> <span data-ttu-id="bde2e-106">Per assicurarsi che questi fusi orari disponibili quando sono necessari, è possibile salvarli serializzando li e ripristinarli in un secondo momento deserializzando li.</span><span class="sxs-lookup"><span data-stu-id="bde2e-106">To ensure that these time zones are available when they are needed, you can save them by serializing them, and later restore them by deserializing them.</span></span>

<span data-ttu-id="bde2e-107">In genere, la serializzazione di un <xref:System.TimeZoneInfo> oggetto si verifica a parte l'applicazione di fuso orario.</span><span class="sxs-lookup"><span data-stu-id="bde2e-107">Typically, serializing a <xref:System.TimeZoneInfo> object occurs apart from the time zone-aware application.</span></span> <span data-ttu-id="bde2e-108">In base all'archivio dati utilizzato per contenere serializzato <xref:System.TimeZoneInfo> oggetti, dati del fuso orario possono essere serializzati come parte di una routine di installazione (ad esempio, quando i dati vengono archiviati in una chiave del Registro di sistema di applicazione) o come parte di una routine di utilità che viene eseguito prima di (ad esempio, quando i dati serializzati vengono archiviati in un file di risorse (resx) XML .NET), viene compilata l'applicazione finale.</span><span class="sxs-lookup"><span data-stu-id="bde2e-108">Depending on the data store used to hold serialized <xref:System.TimeZoneInfo> objects, time zone data may be serialized as part of a setup or installation routine (for example, when the data is stored in an application key of the registry), or as part of a utility routine that runs before the final application is compiled (for example, when the serialized data is stored in a .NET XML resource (.resx) file).</span></span>

<span data-ttu-id="bde2e-109">Oltre a un file di risorse che viene compilato con l'applicazione, è possono utilizzare molti altri archivi dati per informazioni sul fuso orario.</span><span class="sxs-lookup"><span data-stu-id="bde2e-109">In addition to a resource file that is compiled with the application, several other data stores can be used for time zone information.</span></span> <span data-ttu-id="bde2e-110">tra cui:</span><span class="sxs-lookup"><span data-stu-id="bde2e-110">These include the following:</span></span>

* <span data-ttu-id="bde2e-111">Il Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="bde2e-111">The registry.</span></span> <span data-ttu-id="bde2e-112">Si noti che un'applicazione deve utilizzare le sottochiavi della chiave di applicazione per archiviare i dati del fuso orario personalizzato anziché il sottochiavi di HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.</span><span class="sxs-lookup"><span data-stu-id="bde2e-112">Note that an application should use the subkeys of its own application key to store custom time zone data rather than using the subkeys of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.</span></span>

* <span data-ttu-id="bde2e-113">File di configurazione.</span><span class="sxs-lookup"><span data-stu-id="bde2e-113">Configuration files.</span></span>

* <span data-ttu-id="bde2e-114">Altri file di sistema.</span><span class="sxs-lookup"><span data-stu-id="bde2e-114">Other system files.</span></span>

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a><span data-ttu-id="bde2e-115">Per salvare un fuso orario per la serializzazione, in un file con estensione resx</span><span class="sxs-lookup"><span data-stu-id="bde2e-115">To save a time zone by serializing it to a .resx file</span></span>

1. <span data-ttu-id="bde2e-116">Recuperare un fuso orario esistente o creare un nuovo fuso orario.</span><span class="sxs-lookup"><span data-stu-id="bde2e-116">Retrieve an existing time zone or create a new time zone.</span></span>

   <span data-ttu-id="bde2e-117">Per recuperare un fuso orario esistente, vedere [procedura: accedere oggetti fuso UTC e l'ora locali predefiniti](../../../docs/standard/datetime/access-utc-and-local.md) e [procedura: creare un'istanza di un oggetto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md).</span><span class="sxs-lookup"><span data-stu-id="bde2e-117">To retrieve an existing time zone, see [How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md) and [How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md).</span></span>

   <span data-ttu-id="bde2e-118">Per creare un nuovo fuso orario, chiamare uno degli overload di <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="bde2e-118">To create a new time zone, call one of the overloads of the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method.</span></span> <span data-ttu-id="bde2e-119">Per ulteriori informazioni, vedere [procedura: creare fusi orari senza regole di regolazione](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) e [procedura: creare fusi orari con regole di regolazione](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span><span class="sxs-lookup"><span data-stu-id="bde2e-119">For more information, see [How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) and [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span></span>

2. <span data-ttu-id="bde2e-120">Chiamare il <xref:System.TimeZoneInfo.ToSerializedString%2A> metodo per creare una stringa che contiene i dati del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="bde2e-120">Call the <xref:System.TimeZoneInfo.ToSerializedString%2A> method to create a string that contains the time zone's data.</span></span>

3. <span data-ttu-id="bde2e-121">Creare un'istanza di un <xref:System.IO.StreamWriter> fornendo il nome e, facoltativamente, il percorso del file con estensione resx il <xref:System.IO.StreamWriter> costruttore della classe.</span><span class="sxs-lookup"><span data-stu-id="bde2e-121">Instantiate a <xref:System.IO.StreamWriter> object by providing the name and optionally the path of the .resx file to the <xref:System.IO.StreamWriter> class constructor.</span></span>

4. <span data-ttu-id="bde2e-122">Creare un'istanza di un <xref:System.Resources.ResXResourceWriter> oggetto passando il <xref:System.IO.StreamWriter> dell'oggetto per il <xref:System.Resources.ResXResourceWriter> costruttore della classe.</span><span class="sxs-lookup"><span data-stu-id="bde2e-122">Instantiate a <xref:System.Resources.ResXResourceWriter> object by passing the <xref:System.IO.StreamWriter> object to the <xref:System.Resources.ResXResourceWriter> class constructor.</span></span>

5. <span data-ttu-id="bde2e-123">Passare il fuso orario stringa serializzata per il <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="bde2e-123">Pass the time zone's serialized string to the <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> method.</span></span>

6. <span data-ttu-id="bde2e-124">Chiamare il metodo <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bde2e-124">Call the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method.</span></span>

7. <span data-ttu-id="bde2e-125">Chiamare il metodo <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bde2e-125">Call the <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> method.</span></span>

8. <span data-ttu-id="bde2e-126">Chiudi il <xref:System.IO.StreamWriter> oggetto chiamando il relativo <xref:System.IO.StreamWriter.Close%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="bde2e-126">Close the <xref:System.IO.StreamWriter> object by calling its <xref:System.IO.StreamWriter.Close%2A> method.</span></span>

9. <span data-ttu-id="bde2e-127">Aggiungere il file con estensione resx generato al progetto di Visual Studio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bde2e-127">Add the generated .resx file to the application's Visual Studio project.</span></span>

10. <span data-ttu-id="bde2e-128">Utilizzando il **proprietà** finestra in Visual Studio, assicurarsi che il file. resx **azione di compilazione** è impostata su **risorsa incorporata**.</span><span class="sxs-lookup"><span data-stu-id="bde2e-128">Using the **Properties** window in Visual Studio, make sure that the .resx file's **Build Action** property is set to **Embedded Resource**.</span></span>

## <a name="example"></a><span data-ttu-id="bde2e-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="bde2e-129">Example</span></span>

<span data-ttu-id="bde2e-130">Nell'esempio seguente viene serializzata una <xref:System.TimeZoneInfo> oggetto che rappresenta l'ora solare fuso centrale e un <xref:System.TimeZoneInfo> oggetto che rappresenta la stazione Palmer, Antartide a un file di risorse XML .NET denominato SerializedTimeZones.</span><span class="sxs-lookup"><span data-stu-id="bde2e-130">The following example serializes a <xref:System.TimeZoneInfo> object that represents Central Standard Time and a <xref:System.TimeZoneInfo> object that represents the Palmer Station, Antarctica time to a .NET XML resource file that is named SerializedTimeZones.resx.</span></span> <span data-ttu-id="bde2e-131">Ora solare fuso centrale è in genere definito nel Registro di sistema. Palmer stazione, Antartide è un fuso orario personalizzato.</span><span class="sxs-lookup"><span data-stu-id="bde2e-131">Central Standard Time is typically defined in the registry; Palmer Station, Antarctica is a custom time zone.</span></span>

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

<span data-ttu-id="bde2e-132">In questo esempio serializza <xref:System.TimeZoneInfo> oggetti in modo che siano disponibili in un file di risorse in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="bde2e-132">This example serializes <xref:System.TimeZoneInfo> objects so that they are available in a resource file at compile time.</span></span>

<span data-ttu-id="bde2e-133">Poiché il <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> metodo aggiunge informazioni di intestazione completa in un file di risorse XML .NET, e non può essere utilizzato per aggiungere risorse a un file esistente.</span><span class="sxs-lookup"><span data-stu-id="bde2e-133">Because the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method adds complete header information to a .NET XML resource file, it cannot be used to add resources to an existing file.</span></span> <span data-ttu-id="bde2e-134">Nell'esempio viene gestita mediante il controllo per il file SerializedTimeZones e, se presente, archiviando tutte le relative risorse eccetto i due fusi orari serializzati in un oggetto generico <xref:System.Collections.Generic.Dictionary%602> oggetto.</span><span class="sxs-lookup"><span data-stu-id="bde2e-134">The example handles this by checking for the SerializedTimeZones.resx file and, if it exists, storing all of its resources other than the two serialized time zones to a generic <xref:System.Collections.Generic.Dictionary%602> object.</span></span> <span data-ttu-id="bde2e-135">Il file esistente viene eliminato e le risorse esistenti vengono aggiunti a un nuovo file SerializedTimeZones.</span><span class="sxs-lookup"><span data-stu-id="bde2e-135">The existing file is then deleted and the existing resources are added to a new SerializedTimeZones.resx file.</span></span> <span data-ttu-id="bde2e-136">I dati serializzati fuso orario viene anche aggiunto a questo file.</span><span class="sxs-lookup"><span data-stu-id="bde2e-136">The serialized time zone data is also added to this file.</span></span>

<span data-ttu-id="bde2e-137">La chiave (o **nome**) i campi delle risorse non devono contenere spazi.</span><span class="sxs-lookup"><span data-stu-id="bde2e-137">The key (or **Name**) fields of resources should not contain embedded spaces.</span></span> <span data-ttu-id="bde2e-138">Il <xref:System.String.Replace%28System.String%2CSystem.String%29> metodo viene chiamato per rimuovere tutti gli spazi negli identificatori del fuso orario prima che vengano assegnati al file di risorse.</span><span class="sxs-lookup"><span data-stu-id="bde2e-138">The <xref:System.String.Replace%28System.String%2CSystem.String%29> method is called to remove all embedded spaces in the time zone identifiers before they are assigned to the resource file.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="bde2e-139">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="bde2e-139">Compiling the code</span></span>

<span data-ttu-id="bde2e-140">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bde2e-140">This example requires:</span></span>

* <span data-ttu-id="bde2e-141">Un riferimento a System.Core.dll e di Forms essere aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="bde2e-141">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="bde2e-142">Che importati spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bde2e-142">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="bde2e-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bde2e-143">See also</span></span>

<span data-ttu-id="bde2e-144">[Date, ore e fusi orari](../../../docs/standard/datetime/index.md)
[Panoramica sul fuso orario](../../../docs/standard/datetime/time-zone-overview.md)
[procedura: ripristinare fusi orari da una risorsa incorporata](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span><span class="sxs-lookup"><span data-stu-id="bde2e-144">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Time zone overview](../../../docs/standard/datetime/time-zone-overview.md)
[How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span></span>
