---
title: 'Mitigazione: Separatore di percorsi ZipArchiveEntry.FullName'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- ',NET Framework application compatibility'
- .NET Framework 4.6.1
- .NET Framework 4.6.1 retargeting changes
- retargeting changes
ms.assetid: 8d575722-4fb6-49a2-8a06-f72d62dc3766
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c9f271e10014d2f6fb04eb4279b068b7a191639f
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-ziparchiveentryfullname-path-separator"></a><span data-ttu-id="54e27-102">Mitigazione: Separatore di percorsi ZipArchiveEntry.FullName</span><span class="sxs-lookup"><span data-stu-id="54e27-102">Mitigation: ZipArchiveEntry.FullName Path Separator</span></span>
<span data-ttu-id="54e27-103">A partire dalle applicazioni che hanno come destinazione [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], il separatore di percorso usato nella proprietà <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=fullName> è stato modificato dalla barra rovesciata ("\\") usata nelle versioni precedenti di .NET Framework in una barra ("/").</span><span class="sxs-lookup"><span data-stu-id="54e27-103">Starting with apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], the path separator used in the <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=fullName> property has changed from the backslash ("\\") used in previous versions of the .NET Framework to a forward slash ("/").</span></span>   <span data-ttu-id="54e27-104">Gli oggetti <xref:System.IO.Compression.ZipArchiveEntry?displayProperty=fullName> vengono creati chiamando uno degli overload del metodo <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="54e27-104"><xref:System.IO.Compression.ZipArchiveEntry?displayProperty=fullName> objects are created by calling one of the overloads of the <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=fullName> method.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="54e27-105">Impatto</span><span class="sxs-lookup"><span data-stu-id="54e27-105">Impact</span></span>  
 <span data-ttu-id="54e27-106">Questa modifica garantisce la conformità dell'implementazione .NET alla sezione 4.4.17.1 della [specifica relativa al formato di file ZIP](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) e consente agli archivi con estensione ZIP di essere decompressi anche in sistemi non Windows.</span><span class="sxs-lookup"><span data-stu-id="54e27-106">The change brings the .NET implementation into conformity with section 4.4.17.1 of the [.ZIP File Format Specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) and allows .ZIP archives to be decompressed on non-Windows systems.</span></span>  
  
 <span data-ttu-id="54e27-107">La decompressione di un file zip creato da un'applicazione che ha come destinazione una versione precedente di .NET Framework nei sistemi operativi non Windows quali Macintosh non riesce a mantenere la struttura della directory.</span><span class="sxs-lookup"><span data-stu-id="54e27-107">Decompressing a zip file created  by an app that targets a previous version of the .NET Framework on non-Windows operating systems such as the Macintosh fails to preserve the directory structure.</span></span> <span data-ttu-id="54e27-108">Ad esempio, su Macintosh, crea un set di file il cui nome concatena il percorso della directory, insieme a qualsiasi barra rovesciata ("\\") e al nome del file.</span><span class="sxs-lookup"><span data-stu-id="54e27-108">For example, on the Macintosh, it creates a set of files whose filename concatenates the directory path, along with any backslash ("\\") characters, and the filename.</span></span> <span data-ttu-id="54e27-109">Di conseguenza, la struttura di directory dei file decompressi non viene mantenuta.</span><span class="sxs-lookup"><span data-stu-id="54e27-109">As a result, the directory structure of decompressed files is not preserved.</span></span>  
  
 <span data-ttu-id="54e27-110">L'impatto di questa modifica sui file ZIP che vengono decompressi nel sistema operativo Windows dalle API nello spazio dei nomi .NET Framework <xref:System.IO> dovrebbe essere minimo, poiché queste API possono gestire facilmente una barra ("/") o una barra rovesciata ("\\") come carattere separatore di percorso.</span><span class="sxs-lookup"><span data-stu-id="54e27-110">The impact of this change on .ZIP files that are decompressed on the Windows operating system by APIs in the .NET Framework <xref:System.IO> namespace should be minimal, since these APIs can seamlessly handle either a slash ("/") or a backslash ("\\") as the path separator character.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="54e27-111">Mitigazione</span><span class="sxs-lookup"><span data-stu-id="54e27-111">Mitigation</span></span>  
 <span data-ttu-id="54e27-112">Se questo comportamento è inaccettabile, è possibile scegliere di aggiungere un'impostazione di configurazione per la sezione [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="54e27-112">If this behavior is undesirable, you can opt out of by adding a configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file.</span></span> <span data-ttu-id="54e27-113">Di seguito viene illustrato sia la sezione `<runtime>` sia il commutatore di rifiuto.</span><span class="sxs-lookup"><span data-stu-id="54e27-113">The following shows both the `<runtime>` section and the opt-out switch.</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />  
</runtime>  
```  
  
 <span data-ttu-id="54e27-114">Le app destinate a versioni precedenti di .NET Framework ma in esecuzione su [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] o versione successiva possono optare per questo comportamento aggiungendo l'impostazione di configurazione alla sezione [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="54e27-114">In addition, apps that target previous versions of the .NET Framework but are running on the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and later versions can opt in to this behavior by adding a configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file.</span></span> <span data-ttu-id="54e27-115">Di seguito viene illustrato sia la sezione `<runtime>` sia il commutatore di consenso.</span><span class="sxs-lookup"><span data-stu-id="54e27-115">The following shows both the `<runtime>` section and the opt-in switch.</span></span>  
  
```xml  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="54e27-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54e27-116">See Also</span></span>  
 <span data-ttu-id="54e27-117">[Modifiche di reindirizzamento](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md) </span><span class="sxs-lookup"><span data-stu-id="54e27-117">[Retargeting Changes](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md) </span></span>  
 [<span data-ttu-id="54e27-118">Compatibilità delle applicazioni nella versione 4.6.1</span><span class="sxs-lookup"><span data-stu-id="54e27-118">Application Compatibility in 4.6.1</span></span>](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)

