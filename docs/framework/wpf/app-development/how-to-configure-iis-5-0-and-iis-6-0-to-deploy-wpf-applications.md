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
# <a name="how-to-configure-iis-50-and-iis-60-to-deploy-wpf-applications"></a>Procedura: configurare IIS 5.0 e IIS 6.0 per distribuire applicazioni WPF

È possibile distribuire un'applicazione [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] dalla maggior parte dei server Web, purché siano configurati con i tipi di Multipurpose Internet Mail Extensions appropriati (MIME). Per impostazione predefinita, Microsoft Internet Information Services (IIS) 7,0 è configurato con questi tipi MIME, ma Microsoft Internet Information Services (IIS) 5,0 e Microsoft Internet Information Services (IIS) 6,0 non lo sono.

In questo argomento viene descritto come configurare Microsoft Internet Information Services (IIS) 5,0 e Microsoft Internet Information Services (IIS) 6,0 per distribuire [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni.

> [!NOTE]
> È possibile controllare la stringa *UserAgent* nel registro di sistema per determinare se .NET Framework installato un sistema. Per informazioni dettagliate e uno script che esamina la stringa *UserAgent* per determinare se .NET Framework è installato in un sistema, vedere [rilevare se è installato il .NET Framework 3,0](how-to-detect-whether-the-net-framework-3-0-is-installed.md).

<a name="content_expiration"></a>

## <a name="adjust-the-content-expiration-setting"></a>Regolare l'impostazione di scadenza del contenuto

È necessario regolare l'impostazione della scadenza del contenuto su 1 minuto. La procedura seguente illustra come eseguire questa operazione con IIS.

1. Fare clic sul menu **Start**, scegliere **Strumenti di amministrazione**, quindi fare clic su **Gestione Internet Information Services (IIS)** . È anche possibile avviare questa applicazione dalla riga di comando con "%SystemRoot%\system32\inetsrv\iis.msc".

2. Espandere l'albero IIS fino a individuare il nodo **sito Web predefinito** .

3. Fare clic con il pulsante destro del mouse su **Sito Web predefinito** e scegliere **Proprietà** dal menu contestuale.

4. Selezionare la scheda **Intestazioni HTTP** e fare clic su "Abilita scadenza contenuto".

5. Impostare il contenuto in modo che scada dopo 1 minuto.

<a name="register_mime_types"></a>

## <a name="register-mime-types-and-file-extensions"></a>Registrare tipi MIME ed estensioni file

È necessario registrare diversi tipi MIME ed estensioni di file in modo che il browser sul sistema del client possa caricare il gestore corretto. È necessario aggiungere i seguenti tipi:

|Estensione|Tipo MIME|
|---------------|---------------|
|.manifest|application/manifest|
|.xaml|application/xaml+xml|
|.application|application/x-ms-application|
|.xbap|application/x-ms-xbap|
|.deploy|application/octet-stream|
|.xps|application/vnd.ms-xpsdocument|

> [!NOTE]
> Non è necessario registrare tipi MIME o estensioni di file nei sistemi client. Vengono registrati automaticamente quando si installa Microsoft .NET Framework.

Il seguente esempio di Microsoft Visual Basic Scripting Edition (VBScript) aggiunge automaticamente i tipi MIME necessari a IIS. Per utilizzare lo script, copiare il codice in un file con estensione vbs sul server. Eseguire quindi lo script eseguendo il file dalla riga di comando o facendo doppio clic sul file in Esplora risorse di Microsoft Windows.

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
> L'esecuzione di questo script più volte crea più voci della mappa MIME nella metabase Microsoft Internet Information Services (IIS) 5,0 o Microsoft Internet Information Services (IIS) 6,0.

Dopo aver eseguito questo script, è possibile che non vengano visualizzati altri tipi MIME da Microsoft Internet Information Services (IIS) 5,0 o Microsoft Internet Information Services (IIS) 6,0 Microsoft Management Console (MMC). Tuttavia, questi tipi MIME sono stati aggiunti alla metabase Microsoft Internet Information Services (IIS) 5,0 o Microsoft Internet Information Services (IIS) 6,0. Lo script seguente visualizzerà tutti i tipi MIME nella metabase Microsoft Internet Information Services (IIS) 5,0 o Microsoft Internet Information Services (IIS) 6,0.

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

Salvare lo script come file `.vbs` (ad esempio, `DiscoverIISMimeTypes.vbs`) ed eseguirlo dal prompt dei comandi utilizzando il comando seguente:

```console
cscript DiscoverIISMimeTypes.vbs
```
