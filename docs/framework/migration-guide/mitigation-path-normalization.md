---
title: 'Migrazione: Normalizzazione del percorso'
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
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e30099e315f88bd051dca2e1f6c83d1bccc49569
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-path-normalization"></a><span data-ttu-id="bdc93-102">Migrazione: Normalizzazione del percorso</span><span class="sxs-lookup"><span data-stu-id="bdc93-102">Mitigation: Path Normalization</span></span>
<span data-ttu-id="bdc93-103">A partire dalle applicazioni destinate a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], la normalizzazione del percorso in .NET Framework è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="bdc93-103">Starting with apps the target  the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], path normalization in the .NET Framework has changed.</span></span>  
  
## <a name="what-is-path-normalization"></a><span data-ttu-id="bdc93-104">Che cos'è la normalizzazione di un percorso?</span><span class="sxs-lookup"><span data-stu-id="bdc93-104">What is path normalization?</span></span>  
 <span data-ttu-id="bdc93-105">La normalizzazione di un percorso include la modifica della stringa che identifica un file o il percorso in modo che sia conforme a un percorso valido sul sistema operativo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bdc93-105">Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="bdc93-106">In genere, la normalizzazione implica:</span><span class="sxs-lookup"><span data-stu-id="bdc93-106">Normalization typically involves:</span></span>  
  
-   <span data-ttu-id="bdc93-107">La conversione in forma canonica dei separatori di directory e dei componenti.</span><span class="sxs-lookup"><span data-stu-id="bdc93-107">Canonicalizing component and directory separators.</span></span>  
  
-   <span data-ttu-id="bdc93-108">L'applicazione della directory corrente in un percorso relativo.</span><span class="sxs-lookup"><span data-stu-id="bdc93-108">Applying the current directory to a relative path.</span></span>  
  
-   <span data-ttu-id="bdc93-109">La valutazione della directory relativa (`.`) o della directory padre (`..`) in un percorso.</span><span class="sxs-lookup"><span data-stu-id="bdc93-109">Evaluating the relative directory (`.`) or the parent directory (`..`) in a path.</span></span>  
  
-   <span data-ttu-id="bdc93-110">La rimozione di caratteri specificati.</span><span class="sxs-lookup"><span data-stu-id="bdc93-110">Trimming specified characters.</span></span>  
  
## <a name="the-changes"></a><span data-ttu-id="bdc93-111">Le modifiche</span><span class="sxs-lookup"><span data-stu-id="bdc93-111">The changes</span></span>  
 <span data-ttu-id="bdc93-112">A partire dalle applicazioni destinate a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], la normalizzazione è stata modificata così come segue:</span><span class="sxs-lookup"><span data-stu-id="bdc93-112">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], path normalization has changed in the following ways:</span></span>  
  
-   <span data-ttu-id="bdc93-113">Il runtime viene rinviato alla funzione [GetFullPathName](https://msdn.microsoft.com/library/windows/desktop/aa364963\(v=vs.85\).aspx) del sistema operativo per normalizzare i percorsi.</span><span class="sxs-lookup"><span data-stu-id="bdc93-113">The runtime defers to the operating system's [GetFullPathName](https://msdn.microsoft.com/library/windows/desktop/aa364963\(v=vs.85\).aspx) function to normalize paths.</span></span>  
  
-   <span data-ttu-id="bdc93-114">La normalizzazione non consiste più nel rimuovere la fine dei segmenti di directory (ad esempio uno spazio alla fine di un nome di directory).</span><span class="sxs-lookup"><span data-stu-id="bdc93-114">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>  
  
-   <span data-ttu-id="bdc93-115">Supporto per la sintassi del percorso dispositivo in attendibilità totale, tra cui `\\.\` e, per le API del file I/O in mscorlib. dll, `\\?\`.</span><span class="sxs-lookup"><span data-stu-id="bdc93-115">Support for device path syntax in full trust, including  `\\.\` and, for file I/O APIs   in mscorlib.dll, `\\?\`.</span></span>  
  
-   <span data-ttu-id="bdc93-116">Il runtime non convalida i percorsi di sintassi del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bdc93-116">The runtime does not validate device syntax paths.</span></span>  
  
-   <span data-ttu-id="bdc93-117">È supportato l'uso della sintassi del dispositivo per accedere ai flussi di dati alternativi.</span><span class="sxs-lookup"><span data-stu-id="bdc93-117">The use of device syntax to access alternate data streams is supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="bdc93-118">Impatto</span><span class="sxs-lookup"><span data-stu-id="bdc93-118">Impact</span></span>  
 <span data-ttu-id="bdc93-119">Per le applicazioni destinate a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o versioni successive, queste modifiche sono applicate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bdc93-119">For apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later, these changes are on  by default.</span></span> <span data-ttu-id="bdc93-120">Tali modifiche migliorano le prestazioni, consentendo al contempo ai metodi di accedere ai percorsi in precedenza inaccessibili.</span><span class="sxs-lookup"><span data-stu-id="bdc93-120">They should improve performance while allowing methods to access previously inaccessible paths.</span></span>  
  
 <span data-ttu-id="bdc93-121">Le applicazioni destinate a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] e versioni precedenti ma in esecuzione in [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o versioni successive non sono interessate da questa modifica.</span><span class="sxs-lookup"><span data-stu-id="bdc93-121">Apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions but are running under the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later are unaffected by this change.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="bdc93-122">Attenuazione</span><span class="sxs-lookup"><span data-stu-id="bdc93-122">Mitigation</span></span>  
 <span data-ttu-id="bdc93-123">Le app destinate a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o versioni successive possono rifiutare esplicitamente questa modifica e usare la normalizzazione legacy aggiungendo il codice seguente alla sezione [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="bdc93-123">Apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later can opt out of this change and use legacy normalization by adding the following to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
</runtime>  
```  
  
 <span data-ttu-id="bdc93-124">Le app destinate a [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] o versioni precedenti ma in esecuzione su [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] o versioni successive possono abilitare le modifiche alla normalizzazione del percorso aggiungendo la riga seguente alla sezione [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="bdc93-124">Apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] or earlier but are running on the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later can enable the changes to path normalization by adding the following line to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application .configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />    
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bdc93-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bdc93-125">See Also</span></span>  
 [<span data-ttu-id="bdc93-126">Modifiche di reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="bdc93-126">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)

