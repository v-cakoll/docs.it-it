---
title: 'Procedura: salvare fusi orari in una risorsa incorporata'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], saving
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
ms.openlocfilehash: c8084cb8edff64b9d598f4fd0a62a362491c7aa7
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281245"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a><span data-ttu-id="e8ce7-102">Procedura: salvare fusi orari in una risorsa incorporata</span><span class="sxs-lookup"><span data-stu-id="e8ce7-102">How to: Save time zones to an embedded resource</span></span>

<span data-ttu-id="e8ce7-103">Un'applicazione in grado di riconoscere il fuso orario richiede spesso la presenza di un determinato fuso orario.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-103">A time zone-aware application often requires the presence of a particular time zone.</span></span> <span data-ttu-id="e8ce7-104">Tuttavia, poiché la disponibilità di singoli <xref:System.TimeZoneInfo> oggetti dipende dalle informazioni archiviate nel registro di sistema del sistema locale, anche i fusi orari disponibili abitualmente potrebbero essere assenti.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-104">However, because the availability of individual <xref:System.TimeZoneInfo> objects depends on information stored in the local system's registry, even customarily available time zones may be absent.</span></span> <span data-ttu-id="e8ce7-105">Inoltre, le informazioni sui fusi orari personalizzati di cui è stata creata un'istanza tramite il <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo non vengono archiviate con altre informazioni sul fuso orario nel registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-105">In addition, information about custom time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method is not stored with other time zone information in the registry.</span></span> <span data-ttu-id="e8ce7-106">Per assicurarsi che questi fusi orari siano disponibili quando sono necessari, è possibile salvarli mediante la serializzazione e successivamente ripristinarli mediante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-106">To ensure that these time zones are available when they are needed, you can save them by serializing them, and later restore them by deserializing them.</span></span>

<span data-ttu-id="e8ce7-107">In genere, la serializzazione di un <xref:System.TimeZoneInfo> oggetto viene eseguita a parte l'applicazione in grado di riconoscere il fuso orario.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-107">Typically, serializing a <xref:System.TimeZoneInfo> object occurs apart from the time zone-aware application.</span></span> <span data-ttu-id="e8ce7-108">A seconda dell'archivio dati utilizzato per contenere oggetti serializzati <xref:System.TimeZoneInfo> , i dati del fuso orario possono essere serializzati come parte di una routine di installazione o installazione, ad esempio quando i dati vengono archiviati in una chiave dell'applicazione del registro di sistema, o come parte di una routine di utilità eseguita prima che l'applicazione finale venga compilata, ad esempio quando i dati serializzati vengono archiviati in un file di risorse XML (con estensione resx) .NET.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-108">Depending on the data store used to hold serialized <xref:System.TimeZoneInfo> objects, time zone data may be serialized as part of a setup or installation routine (for example, when the data is stored in an application key of the registry), or as part of a utility routine that runs before the final application is compiled (for example, when the serialized data is stored in a .NET XML resource (.resx) file).</span></span>

<span data-ttu-id="e8ce7-109">Oltre a un file di risorse compilato con l'applicazione, è possibile usare diversi altri archivi dati per le informazioni sul fuso orario.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-109">In addition to a resource file that is compiled with the application, several other data stores can be used for time zone information.</span></span> <span data-ttu-id="e8ce7-110">tra cui:</span><span class="sxs-lookup"><span data-stu-id="e8ce7-110">These include the following:</span></span>

- <span data-ttu-id="e8ce7-111">Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-111">The registry.</span></span> <span data-ttu-id="e8ce7-112">Si noti che un'applicazione deve usare le sottochiavi della propria chiave applicativa per archiviare i dati del fuso orario personalizzati anziché usare le sottochiavi di HKEY_LOCAL_MACHINE zone Nt\currentversion\time Zones di \SOFTWARE\Microsoft\Windows.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-112">Note that an application should use the subkeys of its own application key to store custom time zone data rather than using the subkeys of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.</span></span>

- <span data-ttu-id="e8ce7-113">File di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-113">Configuration files.</span></span>

- <span data-ttu-id="e8ce7-114">Altri file di sistema.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-114">Other system files.</span></span>

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a><span data-ttu-id="e8ce7-115">Per salvare un fuso orario eseguendo la serializzazione in un file con estensione resx</span><span class="sxs-lookup"><span data-stu-id="e8ce7-115">To save a time zone by serializing it to a .resx file</span></span>

1. <span data-ttu-id="e8ce7-116">Recuperare un fuso orario esistente o creare un nuovo fuso orario.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-116">Retrieve an existing time zone or create a new time zone.</span></span>

   <span data-ttu-id="e8ce7-117">Per recuperare un fuso orario esistente, vedere [procedura: accedere agli oggetti predefiniti dell'ora UTC e del fuso orario locale](access-utc-and-local.md) e [procedura: creare un'istanza di un oggetto TimeZoneInfo](instantiate-time-zone-info.md).</span><span class="sxs-lookup"><span data-stu-id="e8ce7-117">To retrieve an existing time zone, see [How to: Access the predefined UTC and local time zone objects](access-utc-and-local.md) and [How to: Instantiate a TimeZoneInfo object](instantiate-time-zone-info.md).</span></span>

   <span data-ttu-id="e8ce7-118">Per creare un nuovo fuso orario, chiamare uno degli overload del <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-118">To create a new time zone, call one of the overloads of the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method.</span></span> <span data-ttu-id="e8ce7-119">Per altre informazioni, vedere [procedura: creare fusi orari senza regole di rettifica](create-time-zones-without-adjustment-rules.md) e [procedura: creare fusi orari con regole di rettifica](create-time-zones-with-adjustment-rules.md).</span><span class="sxs-lookup"><span data-stu-id="e8ce7-119">For more information, see [How to: Create time zones without adjustment rules](create-time-zones-without-adjustment-rules.md) and [How to: Create time zones with adjustment rules](create-time-zones-with-adjustment-rules.md).</span></span>

2. <span data-ttu-id="e8ce7-120">Chiamare il <xref:System.TimeZoneInfo.ToSerializedString%2A> metodo per creare una stringa che contiene i dati del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-120">Call the <xref:System.TimeZoneInfo.ToSerializedString%2A> method to create a string that contains the time zone's data.</span></span>

3. <span data-ttu-id="e8ce7-121">Creare un'istanza <xref:System.IO.StreamWriter> di un oggetto fornendo il nome e, facoltativamente, il percorso del file con estensione resx al <xref:System.IO.StreamWriter> costruttore della classe.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-121">Instantiate a <xref:System.IO.StreamWriter> object by providing the name and optionally the path of the .resx file to the <xref:System.IO.StreamWriter> class constructor.</span></span>

4. <span data-ttu-id="e8ce7-122">Creare un'istanza <xref:System.Resources.ResXResourceWriter> di un oggetto passando l' <xref:System.IO.StreamWriter> oggetto al <xref:System.Resources.ResXResourceWriter> costruttore della classe.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-122">Instantiate a <xref:System.Resources.ResXResourceWriter> object by passing the <xref:System.IO.StreamWriter> object to the <xref:System.Resources.ResXResourceWriter> class constructor.</span></span>

5. <span data-ttu-id="e8ce7-123">Passare la stringa serializzata del fuso orario al <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-123">Pass the time zone's serialized string to the <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> method.</span></span>

6. <span data-ttu-id="e8ce7-124">Chiamare il metodo <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e8ce7-124">Call the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method.</span></span>

7. <span data-ttu-id="e8ce7-125">Chiamare il metodo <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e8ce7-125">Call the <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> method.</span></span>

8. <span data-ttu-id="e8ce7-126">Chiudere l' <xref:System.IO.StreamWriter> oggetto chiamando il relativo <xref:System.IO.StreamWriter.Close%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-126">Close the <xref:System.IO.StreamWriter> object by calling its <xref:System.IO.StreamWriter.Close%2A> method.</span></span>

9. <span data-ttu-id="e8ce7-127">Aggiungere il file resx generato al progetto di Visual Studio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-127">Add the generated .resx file to the application's Visual Studio project.</span></span>

10. <span data-ttu-id="e8ce7-128">Utilizzando la finestra **Proprietà** in Visual Studio, assicurarsi che la proprietà **azione di compilazione** del file. resx sia impostata su **risorsa incorporata**.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-128">Using the **Properties** window in Visual Studio, make sure that the .resx file's **Build Action** property is set to **Embedded Resource**.</span></span>

## <a name="example"></a><span data-ttu-id="e8ce7-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8ce7-129">Example</span></span>

<span data-ttu-id="e8ce7-130">Nell'esempio seguente viene serializzato un <xref:System.TimeZoneInfo> oggetto che rappresenta l'ora solare centrale e un <xref:System.TimeZoneInfo> oggetto che rappresenta la stazione di Palmer, l'ora antartica in un file di risorse XML .NET denominato SerializedTimeZones. resx.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-130">The following example serializes a <xref:System.TimeZoneInfo> object that represents Central Standard Time and a <xref:System.TimeZoneInfo> object that represents the Palmer Station, Antarctica time to a .NET XML resource file that is named SerializedTimeZones.resx.</span></span> <span data-ttu-id="e8ce7-131">L'ora solare centrale è in genere definita nel registro di sistema; Palmer Station, Antartide è un fuso orario personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-131">Central Standard Time is typically defined in the registry; Palmer Station, Antarctica is a custom time zone.</span></span>

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

<span data-ttu-id="e8ce7-132">Questo esempio serializza <xref:System.TimeZoneInfo> gli oggetti in modo che siano disponibili in un file di risorse in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-132">This example serializes <xref:System.TimeZoneInfo> objects so that they are available in a resource file at compile time.</span></span>

<span data-ttu-id="e8ce7-133">Poiché il <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> metodo aggiunge informazioni di intestazione complete a un file di risorse XML .NET, non può essere utilizzato per aggiungere risorse a un file esistente.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-133">Because the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method adds complete header information to a .NET XML resource file, it cannot be used to add resources to an existing file.</span></span> <span data-ttu-id="e8ce7-134">L'esempio gestisce questa operazione controllando la presenza del file SerializedTimeZones. resx e, se esiste, archiviando tutte le relative risorse diverse dai due fusi orari serializzati in un <xref:System.Collections.Generic.Dictionary%602> oggetto generico.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-134">The example handles this by checking for the SerializedTimeZones.resx file and, if it exists, storing all of its resources other than the two serialized time zones to a generic <xref:System.Collections.Generic.Dictionary%602> object.</span></span> <span data-ttu-id="e8ce7-135">Il file esistente viene quindi eliminato e le risorse esistenti vengono aggiunte a un nuovo file SerializedTimeZones. resx.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-135">The existing file is then deleted and the existing resources are added to a new SerializedTimeZones.resx file.</span></span> <span data-ttu-id="e8ce7-136">Anche i dati serializzati del fuso orario vengono aggiunti a questo file.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-136">The serialized time zone data is also added to this file.</span></span>

<span data-ttu-id="e8ce7-137">I campi chiave (o **nome**) delle risorse non devono contenere spazi incorporati.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-137">The key (or **Name**) fields of resources should not contain embedded spaces.</span></span> <span data-ttu-id="e8ce7-138">Il <xref:System.String.Replace%28System.String%2CSystem.String%29> metodo viene chiamato per rimuovere tutti gli spazi incorporati negli identificatori del fuso orario prima che vengano assegnati al file di risorse.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-138">The <xref:System.String.Replace%28System.String%2CSystem.String%29> method is called to remove all embedded spaces in the time zone identifiers before they are assigned to the resource file.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="e8ce7-139">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e8ce7-139">Compiling the code</span></span>

<span data-ttu-id="e8ce7-140">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8ce7-140">This example requires:</span></span>

- <span data-ttu-id="e8ce7-141">Che un riferimento a System. Windows. Forms. dll e System. Core. dll venga aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="e8ce7-141">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

- <span data-ttu-id="e8ce7-142">Che vengano importati gli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8ce7-142">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="e8ce7-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8ce7-143">See also</span></span>

- [<span data-ttu-id="e8ce7-144">Date, ore e fusi orari</span><span class="sxs-lookup"><span data-stu-id="e8ce7-144">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="e8ce7-145">Panoramica sul fuso orario</span><span class="sxs-lookup"><span data-stu-id="e8ce7-145">Time zone overview</span></span>](time-zone-overview.md)
- [<span data-ttu-id="e8ce7-146">Procedura: ripristinare i fusi orari da una risorsa incorporata</span><span class="sxs-lookup"><span data-stu-id="e8ce7-146">How to: Restore time zones from an embedded resource</span></span>](restore-time-zones-from-an-embedded-resource.md)
