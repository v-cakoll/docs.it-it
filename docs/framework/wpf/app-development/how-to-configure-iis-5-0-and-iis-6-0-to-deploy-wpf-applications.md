---
title: 'Procedura: configurare IIS 5.0 e IIS 6.0 per distribuire applicazioni WPF'
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- MIME types [WPF], registering
- adjusting content expiration setting [WPF]
- registering file extensions [WPF]
- deploying applications [WPF]
- applications [WPF], deploying
- Web servers [WPF], configuring to deploy WPF applications
- configuring Web servers to deploy WPF applications [WPF]
- content expiration setting [WPF], adjusting
- file extensions [WPF], registering
- registering MIME types [WPF]
ms.assetid: c6e8c2cb-9ba2-4e75-a0d5-180ec9639433
ms.openlocfilehash: d557ac6cd380edcbc93b5315f6356697817274bf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740415"
---
# <a name="how-to-configure-iis-50-and-iis-60-to-deploy-wpf-applications"></a><span data-ttu-id="bbcb1-102">Procedura: configurare IIS 5.0 e IIS 6.0 per distribuire applicazioni WPF</span><span class="sxs-lookup"><span data-stu-id="bbcb1-102">How to: Configure IIS 5.0 and IIS 6.0 to Deploy WPF Applications</span></span>

<span data-ttu-id="bbcb1-103">È possibile distribuire un'applicazione [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] dalla maggior parte dei server Web, purché siano configurati con i tipi di Multipurpose Internet Mail Extensions appropriati (MIME).</span><span class="sxs-lookup"><span data-stu-id="bbcb1-103">You can deploy a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application from most Web servers, as long as they are configured with the appropriate Multipurpose Internet Mail Extensions (MIME) types.</span></span> <span data-ttu-id="bbcb1-104">Per impostazione predefinita, Microsoft Internet Information Services (IIS) 7,0 è configurato con questi tipi MIME, ma Microsoft Internet Information Services (IIS) 5,0 e Microsoft Internet Information Services (IIS) 6,0 non lo sono.</span><span class="sxs-lookup"><span data-stu-id="bbcb1-104">By default, Microsoft Internet Information Services (IIS) 7.0 is configured with these MIME types, but Microsoft Internet Information Services (IIS) 5.0 and Microsoft Internet Information Services (IIS) 6.0 are not.</span></span>

<span data-ttu-id="bbcb1-105">In questo argomento viene descritto come configurare Microsoft Internet Information Services (IIS) 5,0 e Microsoft Internet Information Services (IIS) 6,0 per distribuire [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni.</span><span class="sxs-lookup"><span data-stu-id="bbcb1-105">This topic describes how to configure Microsoft Internet Information Services (IIS) 5.0 and Microsoft Internet Information Services (IIS) 6.0 to deploy [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span>

> [!NOTE]
> <span data-ttu-id="bbcb1-106">È possibile controllare la stringa *UserAgent* nel registro di sistema per determinare se .NET Framework installato un sistema.</span><span class="sxs-lookup"><span data-stu-id="bbcb1-106">You can check the *UserAgent* string in the registry to determine whether a system has .NET Framework installed.</span></span> <span data-ttu-id="bbcb1-107">Per informazioni dettagliate e uno script che esamina la stringa *UserAgent* per determinare se .NET Framework è installato in un sistema, vedere [rilevare se è installato il .NET Framework 3,0](how-to-detect-whether-the-net-framework-3-0-is-installed.md).</span><span class="sxs-lookup"><span data-stu-id="bbcb1-107">For details and a script that examines the *UserAgent* string to determine whether .NET Framework is installed on a system, see [Detect Whether the .NET Framework 3.0 Is Installed](how-to-detect-whether-the-net-framework-3-0-is-installed.md).</span></span>

<a name="content_expiration"></a>

## <a name="adjust-the-content-expiration-setting"></a><span data-ttu-id="bbcb1-108">Regolare l'impostazione di scadenza del contenuto</span><span class="sxs-lookup"><span data-stu-id="bbcb1-108">Adjust the Content Expiration Setting</span></span>

<span data-ttu-id="bbcb1-109">È necessario regolare l'impostazione della scadenza del contenuto su 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="bbcb1-109">You should adjust the content expiration setting to 1 minute.</span></span> <span data-ttu-id="bbcb1-110">La procedura seguente illustra come eseguire questa operazione con IIS.</span><span class="sxs-lookup"><span data-stu-id="bbcb1-110">The following procedure outlines how to do this with IIS.</span></span>

1. <span data-ttu-id="bbcb1-111">Fare clic sul menu **Start**, scegliere **Strumenti di amministrazione**, quindi fare clic su **Gestione Internet Information Services (IIS)** .</span><span class="sxs-lookup"><span data-stu-id="bbcb1-111">Click the **Start** menu, point to **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="bbcb1-112">È anche possibile avviare questa applicazione dalla riga di comando con "%SystemRoot%\system32\inetsrv\iis.msc".</span><span class="sxs-lookup"><span data-stu-id="bbcb1-112">You can also launch this application from the command line with "%SystemRoot%\system32\inetsrv\iis.msc".</span></span>

2. <span data-ttu-id="bbcb1-113">Espandere l'albero IIS fino a individuare il nodo **sito Web predefinito** .</span><span class="sxs-lookup"><span data-stu-id="bbcb1-113">Expand the IIS tree until you find the **Default Web site** node.</span></span>

3. <span data-ttu-id="bbcb1-114">Fare clic con il pulsante destro del mouse su **Sito Web predefinito** e scegliere **Proprietà** dal menu contestuale.</span><span class="sxs-lookup"><span data-stu-id="bbcb1-114">Right-click **Default Web site** and select **Properties** from the context menu.</span></span>

4. <span data-ttu-id="bbcb1-115">Selezionare la scheda **Intestazioni HTTP** e fare clic su "Abilita scadenza contenuto".</span><span class="sxs-lookup"><span data-stu-id="bbcb1-115">Select the **HTTP Headers** tab and click "Enable Content Expiration".</span></span>

5. <span data-ttu-id="bbcb1-116">Impostare il contenuto in modo che scada dopo 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="bbcb1-116">Set the content to expire after 1 minute.</span></span>

<a name="register_mime_types"></a>

## <a name="register-mime-types-and-file-extensions"></a><span data-ttu-id="bbcb1-117">Registrare tipi MIME ed estensioni file</span><span class="sxs-lookup"><span data-stu-id="bbcb1-117">Register MIME Types and File Extensions</span></span>

<span data-ttu-id="bbcb1-118">È necessario registrare diversi tipi MIME ed estensioni di file in modo che il browser sul sistema del client possa caricare il gestore corretto.</span><span class="sxs-lookup"><span data-stu-id="bbcb1-118">You must register several MIME types and file extensions so that the browser on the client's system can load the correct handler.</span></span> <span data-ttu-id="bbcb1-119">È necessario aggiungere i seguenti tipi:</span><span class="sxs-lookup"><span data-stu-id="bbcb1-119">You need to add the following types:</span></span>

|<span data-ttu-id="bbcb1-120">Estensione</span><span class="sxs-lookup"><span data-stu-id="bbcb1-120">Extension</span></span>|<span data-ttu-id="bbcb1-121">Tipo MIME</span><span class="sxs-lookup"><span data-stu-id="bbcb1-121">MIME Type</span></span>|
|---------------|---------------|
|<span data-ttu-id="bbcb1-122">.manifest</span><span class="sxs-lookup"><span data-stu-id="bbcb1-122">.manifest</span></span>|<span data-ttu-id="bbcb1-123">application/manifest</span><span class="sxs-lookup"><span data-stu-id="bbcb1-123">application/manifest</span></span>|
|<span data-ttu-id="bbcb1-124">.xaml</span><span class="sxs-lookup"><span data-stu-id="bbcb1-124">.xaml</span></span>|<span data-ttu-id="bbcb1-125">application/xaml+xml</span><span class="sxs-lookup"><span data-stu-id="bbcb1-125">application/xaml+xml</span></span>|
|<span data-ttu-id="bbcb1-126">.application</span><span class="sxs-lookup"><span data-stu-id="bbcb1-126">.application</span></span>|<span data-ttu-id="bbcb1-127">application/x-ms-application</span><span class="sxs-lookup"><span data-stu-id="bbcb1-127">application/x-ms-application</span></span>|
|<span data-ttu-id="bbcb1-128">.xbap</span><span class="sxs-lookup"><span data-stu-id="bbcb1-128">.xbap</span></span>|<span data-ttu-id="bbcb1-129">application/x-ms-xbap</span><span class="sxs-lookup"><span data-stu-id="bbcb1-129">application/x-ms-xbap</span></span>|
|<span data-ttu-id="bbcb1-130">.deploy</span><span class="sxs-lookup"><span data-stu-id="bbcb1-130">.deploy</span></span>|<span data-ttu-id="bbcb1-131">application/octet-stream</span><span class="sxs-lookup"><span data-stu-id="bbcb1-131">application/octet-stream</span></span>|
|<span data-ttu-id="bbcb1-132">.xps</span><span class="sxs-lookup"><span data-stu-id="bbcb1-132">.xps</span></span>|<span data-ttu-id="bbcb1-133">application/vnd.ms-xpsdocument</span><span class="sxs-lookup"><span data-stu-id="bbcb1-133">application/vnd.ms-xpsdocument</span></span>|

> [!NOTE]
> <span data-ttu-id="bbcb1-134">Non è necessario registrare tipi MIME o estensioni di file nei sistemi client.</span><span class="sxs-lookup"><span data-stu-id="bbcb1-134">You do not need to register MIME types or file extensions on client systems.</span></span> <span data-ttu-id="bbcb1-135">Vengono registrati automaticamente quando si installa Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bbcb1-135">They are registered automatically when you install Microsoft .NET Framework.</span></span>

<span data-ttu-id="bbcb1-136">Il seguente esempio di Microsoft Visual Basic Scripting Edition (VBScript) aggiunge automaticamente i tipi MIME necessari a IIS.</span><span class="sxs-lookup"><span data-stu-id="bbcb1-136">The following Microsoft Visual Basic Scripting Edition (VBScript) sample automatically adds the necessary MIME types to IIS.</span></span> <span data-ttu-id="bbcb1-137">Per utilizzare lo script, copiare il codice in un file con estensione vbs sul server.</span><span class="sxs-lookup"><span data-stu-id="bbcb1-137">To use the script, copy the code to a .vbs file on your server.</span></span> <span data-ttu-id="bbcb1-138">Eseguire quindi lo script eseguendo il file dalla riga di comando o facendo doppio clic sul file in Esplora risorse di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="bbcb1-138">Then, run the script by running the file from the command line or double-clicking the file in Microsoft Windows Explorer.</span></span>

```vb
' This script adds the necessary Windows Presentation Foundation MIME types
' to an IIS Server.
' To use this script, just double-click or execute it from a command line.
' Running this script multiple times results in multiple entries in the IIS MimeMap.

Dim MimeMapObj, MimeMapArray, MimeTypesToAddArray, WshShell, oExec
Const ADS_PROPERTY_UPDATE = 2

' Set the MIME types to be added
MimeTypesToAddArray = Array(".manifest", "application/manifest", ".xaml", _
    "application/xaml+xml", ".application", "application/x-ms-application", _
    ".deploy", "application/octet-stream", ".xbap", "application/x-ms-xbap", _
    ".xps", "application/vnd.ms-xpsdocument")

' Get the MimeMap object
Set MimeMapObj = GetObject("IIS://LocalHost/MimeMap")

' Call AddMimeType for every pair of extension/MIME type
For counter = 0 to UBound(MimeTypesToAddArray) Step 2
    AddMimeType MimeTypesToAddArray(counter), MimeTypesToAddArray(counter+1)
Next

' Create a Shell object
Set WshShell = CreateObject("WScript.Shell")

' Stop and Start the IIS Service
Set oExec = WshShell.Exec("net stop w3svc")
Do While oExec.Status = 0
    WScript.Sleep 100
Loop

Set oExec = WshShell.Exec("net start w3svc")
Do While oExec.Status = 0
    WScript.Sleep 100
Loop

Set oExec = Nothing

' Report status to user
WScript.Echo "Windows Presentation Foundation MIME types have been registered."

' AddMimeType Sub
Sub AddMimeType (Ext, MType)

    ' Get the mappings from the MimeMap property.
    MimeMapArray = MimeMapObj.GetEx("MimeMap")

    ' Add a new mapping.
    i = UBound(MimeMapArray) + 1
    ReDim Preserve MimeMapArray(i)
    Set MimeMapArray(i) = CreateObject("MimeMap")
    MimeMapArray(i).Extension = Ext
    MimeMapArray(i).MimeType = MType
    MimeMapObj.PutEx ADS_PROPERTY_UPDATE, "MimeMap", MimeMapArray
    MimeMapObj.SetInfo

End Sub
```

> [!NOTE]
> <span data-ttu-id="bbcb1-139">L'esecuzione di questo script più volte crea più voci della mappa MIME nella metabase Microsoft Internet Information Services (IIS) 5,0 o Microsoft Internet Information Services (IIS) 6,0.</span><span class="sxs-lookup"><span data-stu-id="bbcb1-139">Running this script multiple times creates multiple MIME map entries in the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 metabase.</span></span>

<span data-ttu-id="bbcb1-140">Dopo aver eseguito questo script, è possibile che non vengano visualizzati altri tipi MIME da Microsoft Internet Information Services (IIS) 5,0 o Microsoft Internet Information Services (IIS) 6,0 Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="bbcb1-140">After you have run this script, you may not see additional MIME types from the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 Microsoft Management Console (MMC).</span></span> <span data-ttu-id="bbcb1-141">Tuttavia, questi tipi MIME sono stati aggiunti alla metabase Microsoft Internet Information Services (IIS) 5,0 o Microsoft Internet Information Services (IIS) 6,0.</span><span class="sxs-lookup"><span data-stu-id="bbcb1-141">However, these MIME types have been added to the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 metabase.</span></span> <span data-ttu-id="bbcb1-142">Lo script seguente visualizzerà tutti i tipi MIME nella metabase Microsoft Internet Information Services (IIS) 5,0 o Microsoft Internet Information Services (IIS) 6,0.</span><span class="sxs-lookup"><span data-stu-id="bbcb1-142">The following script will display all the MIME types in the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 metabase.</span></span>

```vb
' This script lists the MIME types for an IIS Server.
' To use this script, just double-click or execute it from a command line
' by calling cscript.exe

dim mimeMapEntry, allMimeMaps

' Get the MimeMap object.
Set mimeMapEntry = GetObject("IIS://localhost/MimeMap")
allMimeMaps = mimeMapEntry.GetEx("MimeMap")

' Display the mappings in the table.
For Each mimeMap In allMimeMaps
    WScript.Echo(mimeMap.MimeType & " (" & mimeMap.Extension + ")")
Next
```

<span data-ttu-id="bbcb1-143">Salvare lo script come file `.vbs` (ad esempio, `DiscoverIISMimeTypes.vbs`) ed eseguirlo dal prompt dei comandi utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="bbcb1-143">Save the script as a `.vbs` file (for example, `DiscoverIISMimeTypes.vbs`) and run it from the command prompt using the following command:</span></span>

```console
cscript DiscoverIISMimeTypes.vbs
```
