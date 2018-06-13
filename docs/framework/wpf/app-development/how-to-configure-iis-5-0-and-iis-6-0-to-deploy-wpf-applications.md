---
title: 'Procedura: configurare IIS 5.0 e IIS 6.0 per distribuire applicazioni WPF'
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
ms.openlocfilehash: 7638c6c9af5394838ac584e4dd9a9ca4cfbf8af0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547927"
---
# <a name="how-to-configure-iis-50-and-iis-60-to-deploy-wpf-applications"></a><span data-ttu-id="902de-102">Procedura: configurare IIS 5.0 e IIS 6.0 per distribuire applicazioni WPF</span><span class="sxs-lookup"><span data-stu-id="902de-102">How to: Configure IIS 5.0 and IIS 6.0 to Deploy WPF Applications</span></span>
<span data-ttu-id="902de-103">È possibile distribuire un'applicazione [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] dalla maggior parte dei server Web, purché siano configurati con i tipi [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] appropriati.</span><span class="sxs-lookup"><span data-stu-id="902de-103">You can deploy a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application from most Web servers, as long as they are configured with the appropriate [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] types.</span></span> <span data-ttu-id="902de-104">Per impostazione predefinita, [!INCLUDE[TLA#tla_iis70](../../../../includes/tlasharptla-iis70-md.md)] è configurato con questi tipi [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)], tuttavia [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] e [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] non lo sono.</span><span class="sxs-lookup"><span data-stu-id="902de-104">By default, [!INCLUDE[TLA#tla_iis70](../../../../includes/tlasharptla-iis70-md.md)] is configured with these [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types, but [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] and [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] are not.</span></span>  
  
 <span data-ttu-id="902de-105">Questo argomento descrive come configurare [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] e [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] per distribuire le applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="902de-105">This topic describes how to configure [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] and [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] to deploy [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span>  
  
  
> [!NOTE]
>  <span data-ttu-id="902de-106">È possibile controllare la *UserAgent* stringa nel Registro di sistema per determinare se un sistema è installato .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="902de-106">You can check the *UserAgent* string in the registry to determine whether a system has .NET Framework installed.</span></span> <span data-ttu-id="902de-107">Per informazioni dettagliate e uno script che esamina il *UserAgent* stringa per determinare se è installato .NET Framework in un sistema, vedere [rilevare se il .NET Framework 3.0 è installato](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md).</span><span class="sxs-lookup"><span data-stu-id="902de-107">For details and a script that examines the *UserAgent* string to determine whether .NET Framework is installed on a system, see [Detect Whether the .NET Framework 3.0 Is Installed](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md).</span></span>  
  
<a name="content_expiration"></a>   
## <a name="adjust-the-content-expiration-setting"></a><span data-ttu-id="902de-108">Regolare l'impostazione di scadenza del contenuto</span><span class="sxs-lookup"><span data-stu-id="902de-108">Adjust the Content Expiration Setting</span></span>  
 <span data-ttu-id="902de-109">È necessario regolare l'impostazione della scadenza del contenuto su 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="902de-109">You should adjust the content expiration setting to 1 minute.</span></span> <span data-ttu-id="902de-110">Di seguito viene illustrato come eseguire questa operazione con [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].</span><span class="sxs-lookup"><span data-stu-id="902de-110">The following procedure outlines how to do this with [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].</span></span>  
  
1.  <span data-ttu-id="902de-111">Fare clic sul menu **Start**, scegliere **Strumenti di amministrazione**, quindi fare clic su **Gestione Internet Information Services (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="902de-111">Click the **Start** menu, point to **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="902de-112">È anche possibile avviare questa applicazione dalla riga di comando con "%SystemRoot%\system32\inetsrv\iis.msc".</span><span class="sxs-lookup"><span data-stu-id="902de-112">You can also launch this application from the command line with "%SystemRoot%\system32\inetsrv\iis.msc".</span></span>  
  
2.  <span data-ttu-id="902de-113">Espandere la struttura ad albero di [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)] fino a trovare il nodo **Sito Web predefinito**.</span><span class="sxs-lookup"><span data-stu-id="902de-113">Expand the [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)] tree until you find the **Default Web site** node.</span></span>  
  
3.  <span data-ttu-id="902de-114">Fare clic con il pulsante destro del mouse su **Sito Web predefinito** e scegliere **Proprietà** dal menu contestuale.</span><span class="sxs-lookup"><span data-stu-id="902de-114">Right-click **Default Web site** and select **Properties** from the context menu.</span></span>  
  
4.  <span data-ttu-id="902de-115">Selezionare la scheda **Intestazioni HTTP** e fare clic su "Abilita scadenza contenuto".</span><span class="sxs-lookup"><span data-stu-id="902de-115">Select the **HTTP Headers** tab and click "Enable Content Expiration".</span></span>  
  
5.  <span data-ttu-id="902de-116">Impostare il contenuto in modo che scada dopo 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="902de-116">Set the content to expire after 1 minute.</span></span>  
  
<a name="register_mime_types"></a>   
## <a name="register-mime-types-and-file-extensions"></a><span data-ttu-id="902de-117">Registrare tipi MIME ed estensioni file</span><span class="sxs-lookup"><span data-stu-id="902de-117">Register MIME Types and File Extensions</span></span>  
 <span data-ttu-id="902de-118">Per consentire al browser sul sistema del client di caricare il gestore corretto, occorre registrare diversi tipi [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] ed estensioni file.</span><span class="sxs-lookup"><span data-stu-id="902de-118">You must register several [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types and file extensions so that the browser on the client's system can load the correct handler.</span></span> <span data-ttu-id="902de-119">È necessario aggiungere i seguenti tipi:</span><span class="sxs-lookup"><span data-stu-id="902de-119">You need to add the following types:</span></span>  
  
|<span data-ttu-id="902de-120">Estensione</span><span class="sxs-lookup"><span data-stu-id="902de-120">Extension</span></span>|<span data-ttu-id="902de-121">Tipo MIME</span><span class="sxs-lookup"><span data-stu-id="902de-121">MIME Type</span></span>|  
|---------------|---------------|  
|<span data-ttu-id="902de-122">.manifest</span><span class="sxs-lookup"><span data-stu-id="902de-122">.manifest</span></span>|<span data-ttu-id="902de-123">application/manifest</span><span class="sxs-lookup"><span data-stu-id="902de-123">application/manifest</span></span>|  
|<span data-ttu-id="902de-124">.xaml</span><span class="sxs-lookup"><span data-stu-id="902de-124">.xaml</span></span>|<span data-ttu-id="902de-125">application/xaml+xml</span><span class="sxs-lookup"><span data-stu-id="902de-125">application/xaml+xml</span></span>|  
|<span data-ttu-id="902de-126">.application</span><span class="sxs-lookup"><span data-stu-id="902de-126">.application</span></span>|<span data-ttu-id="902de-127">application/x-ms-application</span><span class="sxs-lookup"><span data-stu-id="902de-127">application/x-ms-application</span></span>|  
|<span data-ttu-id="902de-128">.xbap</span><span class="sxs-lookup"><span data-stu-id="902de-128">.xbap</span></span>|<span data-ttu-id="902de-129">application/x-ms-xbap</span><span class="sxs-lookup"><span data-stu-id="902de-129">application/x-ms-xbap</span></span>|  
|<span data-ttu-id="902de-130">.deploy</span><span class="sxs-lookup"><span data-stu-id="902de-130">.deploy</span></span>|<span data-ttu-id="902de-131">application/octet-stream</span><span class="sxs-lookup"><span data-stu-id="902de-131">application/octet-stream</span></span>|  
|<span data-ttu-id="902de-132">.xps</span><span class="sxs-lookup"><span data-stu-id="902de-132">.xps</span></span>|<span data-ttu-id="902de-133">application/vnd.ms-xpsdocument</span><span class="sxs-lookup"><span data-stu-id="902de-133">application/vnd.ms-xpsdocument</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="902de-134">Non è necessario registrare tipi [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] o estensioni file nei sistemi client.</span><span class="sxs-lookup"><span data-stu-id="902de-134">You do not need to register [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types or file extensions on client systems.</span></span> <span data-ttu-id="902de-135">Questi vengono registrati automaticamente quando si installa Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="902de-135">They are registered automatically when you install Microsoft .NET Framework.</span></span>  
  
 <span data-ttu-id="902de-136">L'esempio di Microsoft Visual Basic, Scripting Edition (VBScript) seguente necessari vengono aggiunti automaticamente [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] tipi di [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].</span><span class="sxs-lookup"><span data-stu-id="902de-136">The following Microsoft Visual Basic Scripting Edition (VBScript) sample automatically adds the necessary [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types to [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].</span></span> <span data-ttu-id="902de-137">Per utilizzare lo script, copiare il codice in un file con estensione vbs sul server.</span><span class="sxs-lookup"><span data-stu-id="902de-137">To use the script, copy the code to a .vbs file on your server.</span></span> <span data-ttu-id="902de-138">Quindi, eseguire lo script eseguendo il file dalla riga di comando oppure facendo doppio clic sul file in [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)].</span><span class="sxs-lookup"><span data-stu-id="902de-138">Then, run the script by running the file from the command line or double-clicking the file in [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)].</span></span>  
  
```  
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
  
' Get the mimemap object   
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
    Redim Preserve MimeMapArray(i)   
    Set MimeMapArray(i) = CreateObject("MimeMap")   
    MimeMapArray(i).Extension = Ext   
    MimeMapArray(i).MimeType = MType   
    MimeMapObj.PutEx ADS_PROPERTY_UPDATE, "MimeMap", MimeMapArray  
    MimeMapObj.SetInfo  
  
End Sub  
```  
  
> [!NOTE]
>  <span data-ttu-id="902de-139">Se lo script viene eseguito più volte, si creano voci di mapping [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] multiple nella metabase [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] o [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)].</span><span class="sxs-lookup"><span data-stu-id="902de-139">Running this script multiple times creates multiple [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] map entries in the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] metabase.</span></span>  
  
 <span data-ttu-id="902de-140">Dopo avere eseguito questo script, potrebbe non essere possibile visualizzare tipi [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] aggiuntivi da [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] o [!INCLUDE[TLA#tla_mmc](../../../../includes/tlasharptla-mmc-md.md)] di [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)].</span><span class="sxs-lookup"><span data-stu-id="902de-140">After you have run this script, you may not see additional [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types from the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] [!INCLUDE[TLA#tla_mmc](../../../../includes/tlasharptla-mmc-md.md)].</span></span> <span data-ttu-id="902de-141">Tuttavia, questi tipi [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] sono stati aggiunti alla metabase [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] o [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)].</span><span class="sxs-lookup"><span data-stu-id="902de-141">However, these [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types have been added to the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] metabase.</span></span> <span data-ttu-id="902de-142">Mediante lo script seguente saranno visualizzati tutti i tipi [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] nella metabase [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] o [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)].</span><span class="sxs-lookup"><span data-stu-id="902de-142">The following script will display all the [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types in the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] metabase.</span></span>  
  
```  
' This script lists the MIME types for an IIS Server.  
' To use this script, just double-click or execute it from a command line   
' by calling cscript.exe  
  
dim mimeMapEntry, allMimeMaps  
  
' Get the mimemap object.  
Set mimeMapEntry = GetObject("IIS://localhost/MimeMap")  
allMimeMaps = mimeMapEntry.GetEx("MimeMap")  
  
' Display the mappings in the table.  
For Each mimeMap In allMimeMaps  
    WScript.Echo(mimeMap.MimeType & " (" & mimeMap.Extension + ")")  
Next  
```  
  
 <span data-ttu-id="902de-143">Salvare lo script come file `.vbs` (ad esempio, `DiscoverIISMimeTypes.vbs`) ed eseguirlo dal prompt dei comandi utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="902de-143">Save the script as a `.vbs` file (for example, `DiscoverIISMimeTypes.vbs`) and run it from the command prompt using the following command:</span></span>  
  
 `cscript DiscoverIISMimeTypes.vbs`
