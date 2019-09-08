---
title: 'Mitigazione: Normalizzazione del percorso'
ms.date: 03/30/2017
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc5ea69d80a225adfc2f409e8303ee1c241398db
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70779339"
---
# <a name="mitigation-path-normalization"></a><span data-ttu-id="ce66f-102">Mitigazione: Normalizzazione del percorso</span><span class="sxs-lookup"><span data-stu-id="ce66f-102">Mitigation: Path Normalization</span></span>
<span data-ttu-id="ce66f-103">A partire dalle applicazioni destinate a .NET Framework 4.6.2, la normalizzazione del percorso in .NET Framework è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="ce66f-103">Starting with apps the target  the .NET Framework 4.6.2, path normalization in the .NET Framework has changed.</span></span>  
  
## <a name="what-is-path-normalization"></a><span data-ttu-id="ce66f-104">Che cos'è la normalizzazione di un percorso?</span><span class="sxs-lookup"><span data-stu-id="ce66f-104">What is path normalization?</span></span>  
 <span data-ttu-id="ce66f-105">La normalizzazione di un percorso include la modifica della stringa che identifica un file o il percorso in modo che sia conforme a un percorso valido sul sistema operativo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ce66f-105">Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="ce66f-106">In genere, la normalizzazione implica:</span><span class="sxs-lookup"><span data-stu-id="ce66f-106">Normalization typically involves:</span></span>  
  
- <span data-ttu-id="ce66f-107">La conversione in forma canonica dei separatori di directory e dei componenti.</span><span class="sxs-lookup"><span data-stu-id="ce66f-107">Canonicalizing component and directory separators.</span></span>  
  
- <span data-ttu-id="ce66f-108">L'applicazione della directory corrente in un percorso relativo.</span><span class="sxs-lookup"><span data-stu-id="ce66f-108">Applying the current directory to a relative path.</span></span>  
  
- <span data-ttu-id="ce66f-109">La valutazione della directory relativa (`.`) o della directory padre (`..`) in un percorso.</span><span class="sxs-lookup"><span data-stu-id="ce66f-109">Evaluating the relative directory (`.`) or the parent directory (`..`) in a path.</span></span>  
  
- <span data-ttu-id="ce66f-110">La rimozione di caratteri specificati.</span><span class="sxs-lookup"><span data-stu-id="ce66f-110">Trimming specified characters.</span></span>  
  
## <a name="the-changes"></a><span data-ttu-id="ce66f-111">Le modifiche</span><span class="sxs-lookup"><span data-stu-id="ce66f-111">The changes</span></span>  
 <span data-ttu-id="ce66f-112">A partire dalle applicazioni destinate a .NET Framework 4.6.2, la normalizzazione del percorso è stata modificata come segue:</span><span class="sxs-lookup"><span data-stu-id="ce66f-112">Starting with apps that target the .NET Framework 4.6.2, path normalization has changed in the following ways:</span></span>  
  
- <span data-ttu-id="ce66f-113">Il runtime viene rinviato alla funzione [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) del sistema operativo per normalizzare i percorsi.</span><span class="sxs-lookup"><span data-stu-id="ce66f-113">The runtime defers to the operating system's [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) function to normalize paths.</span></span>  
  
- <span data-ttu-id="ce66f-114">La normalizzazione non consiste più nel rimuovere la fine dei segmenti di directory (ad esempio uno spazio alla fine di un nome di directory).</span><span class="sxs-lookup"><span data-stu-id="ce66f-114">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>  
  
- <span data-ttu-id="ce66f-115">Supporto per la sintassi del percorso dispositivo in attendibilità totale, tra cui `\\.\` e, per le API del file I/O in mscorlib. dll, `\\?\`.</span><span class="sxs-lookup"><span data-stu-id="ce66f-115">Support for device path syntax in full trust, including  `\\.\` and, for file I/O APIs   in mscorlib.dll, `\\?\`.</span></span>  
  
- <span data-ttu-id="ce66f-116">Il runtime non convalida i percorsi di sintassi del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ce66f-116">The runtime does not validate device syntax paths.</span></span>  
  
- <span data-ttu-id="ce66f-117">È supportato l'uso della sintassi del dispositivo per accedere ai flussi di dati alternativi.</span><span class="sxs-lookup"><span data-stu-id="ce66f-117">The use of device syntax to access alternate data streams is supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="ce66f-118">Impatto</span><span class="sxs-lookup"><span data-stu-id="ce66f-118">Impact</span></span>  

<span data-ttu-id="ce66f-119">Per le applicazioni destinate a .NET Framework 4.6.2 o versioni successive, queste modifiche sono applicate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ce66f-119">For apps that target the .NET Framework 4.6.2 or later, these changes are on  by default.</span></span> <span data-ttu-id="ce66f-120">Tali modifiche migliorano le prestazioni, consentendo al contempo ai metodi di accedere ai percorsi in precedenza inaccessibili.</span><span class="sxs-lookup"><span data-stu-id="ce66f-120">They should improve performance while allowing methods to access previously inaccessible paths.</span></span>  
  
<span data-ttu-id="ce66f-121">Le applicazioni destinate a .NET Framework 4.6.1 e versioni precedenti ma in esecuzione in .NET Framework 4.6.2 o versioni successive non sono interessate da questa modifica.</span><span class="sxs-lookup"><span data-stu-id="ce66f-121">Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="ce66f-122">Mitigazione</span><span class="sxs-lookup"><span data-stu-id="ce66f-122">Mitigation</span></span>  
 <span data-ttu-id="ce66f-123">Le app destinate a .NET Framework 4.6.2 o versioni successive possono rifiutare esplicitamente questa modifica e usare la normalizzazione legacy aggiungendo il codice seguente alla sezione [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="ce66f-123">Apps that target the .NET Framework 4.6.2 or later can opt out of this change and use legacy normalization by adding the following to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
</runtime>  
```  
  
<span data-ttu-id="ce66f-124">Le app destinate a .NET Framework 4.6.1 o versioni precedenti ma in esecuzione su .NET Framework 4.6.2 o versioni successive possono abilitare le modifiche alla normalizzazione del percorso aggiungendo la riga seguente alla sezione [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="ce66f-124">Apps that target the .NET Framework 4.6.1 or earlier but are running on the .NET Framework 4.6.2 or later can enable the changes to path normalization by adding the following line to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application .configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />    
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce66f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce66f-125">See also</span></span>

- [<span data-ttu-id="ce66f-126">Modifiche di reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="ce66f-126">Retargeting Changes</span></span>](retargeting-changes-in-the-net-framework-4-6-2.md)
