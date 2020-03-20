---
title: 'Mitigazione: Separatore di percorsi ZipArchiveEntry.FullName'
ms.date: 03/30/2017
helpviewer_keywords:
- application compatibility
- ',NET Framework application compatibility'
- .NET Framework 4.6.1
- .NET Framework 4.6.1 retargeting changes
- retargeting changes
ms.assetid: 8d575722-4fb6-49a2-8a06-f72d62dc3766
ms.openlocfilehash: 021d22e90ba39a4d01cf7d64588fab2d724b6640
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457726"
---
# <a name="mitigation-ziparchiveentryfullname-path-separator"></a><span data-ttu-id="90dbf-102">Mitigazione: Separatore di percorsi ZipArchiveEntry.FullName</span><span class="sxs-lookup"><span data-stu-id="90dbf-102">Mitigation: ZipArchiveEntry.FullName Path Separator</span></span>
<span data-ttu-id="90dbf-103">A partire dalle applicazioni che hanno come destinazione .NET Framework 4.6.1, il separatore di percorso usato nella proprietà <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> è stato modificato dalla barra rovesciata ("\\"), usata nelle versioni precedenti di .NET Framework, in una barra ("/").</span><span class="sxs-lookup"><span data-stu-id="90dbf-103">Starting with apps that target the .NET Framework 4.6.1, the path separator used in the <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> property has changed from the backslash ("\\") used in previous versions of the .NET Framework to a forward slash ("/").</span></span>   <span data-ttu-id="90dbf-104">Gli oggetti <xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType> vengono creati chiamando uno degli overload del metodo <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="90dbf-104"><xref:System.IO.Compression.ZipArchiveEntry?displayProperty=nameWithType> objects are created by calling one of the overloads of the <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="90dbf-105">Impatto</span><span class="sxs-lookup"><span data-stu-id="90dbf-105">Impact</span></span>  
 <span data-ttu-id="90dbf-106">Questa modifica garantisce la conformità dell'implementazione .NET alla sezione 4.4.17.1 della [specifica relativa al formato di file ZIP](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) e consente agli archivi con estensione ZIP di essere decompressi anche in sistemi non Windows.</span><span class="sxs-lookup"><span data-stu-id="90dbf-106">The change brings the .NET implementation into conformity with section 4.4.17.1 of the [.ZIP File Format Specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) and allows .ZIP archives to be decompressed on non-Windows systems.</span></span>  
  
 <span data-ttu-id="90dbf-107">La decompressione di un file zip creato da un'applicazione che ha come destinazione una versione precedente di .NET Framework nei sistemi operativi non Windows quali Macintosh non riesce a mantenere la struttura della directory.</span><span class="sxs-lookup"><span data-stu-id="90dbf-107">Decompressing a zip file created  by an app that targets a previous version of the .NET Framework on non-Windows operating systems such as the Macintosh fails to preserve the directory structure.</span></span> <span data-ttu-id="90dbf-108">Ad esempio, su Macintosh, crea un set di file il cui nome concatena il percorso della directory, insieme a qualsiasi barra rovesciata ("\\") e al nome del file.</span><span class="sxs-lookup"><span data-stu-id="90dbf-108">For example, on the Macintosh, it creates a set of files whose filename concatenates the directory path, along with any backslash ("\\") characters, and the filename.</span></span> <span data-ttu-id="90dbf-109">Di conseguenza, la struttura di directory dei file decompressi non viene mantenuta.</span><span class="sxs-lookup"><span data-stu-id="90dbf-109">As a result, the directory structure of decompressed files is not preserved.</span></span>  
  
 <span data-ttu-id="90dbf-110">L'impatto di questa modifica sui file ZIP che vengono decompressi nel sistema operativo Windows dalle API nello spazio dei nomi .NET Framework <xref:System.IO> dovrebbe essere minimo, poiché queste API possono gestire facilmente una barra ("/") o una barra rovesciata ("\\") come carattere separatore di percorso.</span><span class="sxs-lookup"><span data-stu-id="90dbf-110">The impact of this change on .ZIP files that are decompressed on the Windows operating system by APIs in the .NET Framework <xref:System.IO> namespace should be minimal, since these APIs can seamlessly handle either a slash ("/") or a backslash ("\\") as the path separator character.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="90dbf-111">Strategia di riduzione del rischio</span><span class="sxs-lookup"><span data-stu-id="90dbf-111">Mitigation</span></span>  
 <span data-ttu-id="90dbf-112">Se questo comportamento è indesiderato, è possibile rifiutare [ \<](../configure-apps/file-schema/runtime/runtime-element.md) esplicitamente aggiungendo un'impostazione di configurazione alla sezione>di runtime del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="90dbf-112">If this behavior is undesirable, you can opt out of by adding a configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file.</span></span> <span data-ttu-id="90dbf-113">Di seguito viene illustrato sia la sezione `<runtime>` sia il commutatore di rifiuto.</span><span class="sxs-lookup"><span data-stu-id="90dbf-113">The following shows both the `<runtime>` section and the opt-out switch.</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />  
</runtime>  
```  
  
 <span data-ttu-id="90dbf-114">Inoltre, le app destinate alle versioni precedenti di .NET Framework ma in esecuzione su .NET Framework 4.6.1 [ \<](../configure-apps/file-schema/runtime/runtime-element.md) e versioni successive possono acconsentire esplicitamente a questo comportamento aggiungendo un'impostazione di configurazione alla sezione>di runtime del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="90dbf-114">In addition, apps that target previous versions of the .NET Framework but are running on the .NET Framework 4.6.1 and later versions can opt in to this behavior by adding a configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file.</span></span> <span data-ttu-id="90dbf-115">Di seguito viene illustrato sia la sezione `<runtime>` sia il commutatore di consenso.</span><span class="sxs-lookup"><span data-stu-id="90dbf-115">The following shows both the `<runtime>` section and the opt-in switch.</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="90dbf-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90dbf-116">See also</span></span>

- [<span data-ttu-id="90dbf-117">Reindirizzamento delle modifiche</span><span class="sxs-lookup"><span data-stu-id="90dbf-117">Retargeting Changes</span></span>](retargeting-changes-in-the-net-framework-4-6-1.md)
- [<span data-ttu-id="90dbf-118">Compatibilità tra le versioni</span><span class="sxs-lookup"><span data-stu-id="90dbf-118">Application compatibility</span></span>](application-compatibility.md)
