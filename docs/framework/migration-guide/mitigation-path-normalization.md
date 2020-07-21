---
title: 'Migrazione: Normalizzazione del percorso'
description: Informazioni sul modo in cui la normalizzazione dei percorsi in .NET Framework è cambiata a partire dalle app destinate a .NET Framework 4.6.2.
ms.date: 03/30/2017
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
ms.openlocfilehash: 89dcc46d9f266ffd3635dc0cc02b634720356eda
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475216"
---
# <a name="mitigation-path-normalization"></a><span data-ttu-id="6d32a-103">Migrazione: Normalizzazione del percorso</span><span class="sxs-lookup"><span data-stu-id="6d32a-103">Mitigation: Path Normalization</span></span>
<span data-ttu-id="6d32a-104">A partire dalle app destinate a .NET Framework 4.6.2, la normalizzazione del percorso nel .NET Framework è cambiata.</span><span class="sxs-lookup"><span data-stu-id="6d32a-104">Starting with apps that target .NET Framework 4.6.2, path normalization in the .NET Framework has changed.</span></span>  
  
## <a name="what-is-path-normalization"></a><span data-ttu-id="6d32a-105">Che cos'è la normalizzazione di un percorso?</span><span class="sxs-lookup"><span data-stu-id="6d32a-105">What is path normalization?</span></span>  
 <span data-ttu-id="6d32a-106">La normalizzazione di un percorso include la modifica della stringa che identifica un file o il percorso in modo che sia conforme a un percorso valido sul sistema operativo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6d32a-106">Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="6d32a-107">In genere, la normalizzazione implica:</span><span class="sxs-lookup"><span data-stu-id="6d32a-107">Normalization typically involves:</span></span>  
  
- <span data-ttu-id="6d32a-108">La conversione in forma canonica dei separatori di directory e dei componenti.</span><span class="sxs-lookup"><span data-stu-id="6d32a-108">Canonicalizing component and directory separators.</span></span>  
  
- <span data-ttu-id="6d32a-109">L'applicazione della directory corrente in un percorso relativo.</span><span class="sxs-lookup"><span data-stu-id="6d32a-109">Applying the current directory to a relative path.</span></span>  
  
- <span data-ttu-id="6d32a-110">La valutazione della directory relativa (`.`) o della directory padre (`..`) in un percorso.</span><span class="sxs-lookup"><span data-stu-id="6d32a-110">Evaluating the relative directory (`.`) or the parent directory (`..`) in a path.</span></span>  
  
- <span data-ttu-id="6d32a-111">La rimozione di caratteri specificati.</span><span class="sxs-lookup"><span data-stu-id="6d32a-111">Trimming specified characters.</span></span>  
  
## <a name="the-changes"></a><span data-ttu-id="6d32a-112">Le modifiche</span><span class="sxs-lookup"><span data-stu-id="6d32a-112">The changes</span></span>  
 <span data-ttu-id="6d32a-113">A partire dalle applicazioni destinate a .NET Framework 4.6.2, la normalizzazione del percorso è stata modificata come segue:</span><span class="sxs-lookup"><span data-stu-id="6d32a-113">Starting with apps that target the .NET Framework 4.6.2, path normalization has changed in the following ways:</span></span>  
  
- <span data-ttu-id="6d32a-114">Il runtime viene rinviato alla funzione [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) del sistema operativo per normalizzare i percorsi.</span><span class="sxs-lookup"><span data-stu-id="6d32a-114">The runtime defers to the operating system's [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) function to normalize paths.</span></span>  
  
- <span data-ttu-id="6d32a-115">La normalizzazione non consiste più nel rimuovere la fine dei segmenti di directory (ad esempio uno spazio alla fine di un nome di directory).</span><span class="sxs-lookup"><span data-stu-id="6d32a-115">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>  
  
- <span data-ttu-id="6d32a-116">Supporto per la sintassi del percorso dispositivo in attendibilità totale, tra cui `\\.\` e, per le API del file I/O in mscorlib. dll, `\\?\`.</span><span class="sxs-lookup"><span data-stu-id="6d32a-116">Support for device path syntax in full trust, including  `\\.\` and, for file I/O APIs   in mscorlib.dll, `\\?\`.</span></span>  
  
- <span data-ttu-id="6d32a-117">Il runtime non convalida i percorsi di sintassi del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6d32a-117">The runtime does not validate device syntax paths.</span></span>  
  
- <span data-ttu-id="6d32a-118">È supportato l'uso della sintassi del dispositivo per accedere ai flussi di dati alternativi.</span><span class="sxs-lookup"><span data-stu-id="6d32a-118">The use of device syntax to access alternate data streams is supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="6d32a-119">Impatto</span><span class="sxs-lookup"><span data-stu-id="6d32a-119">Impact</span></span>  

<span data-ttu-id="6d32a-120">Per le applicazioni destinate a .NET Framework 4.6.2 o versioni successive, queste modifiche sono applicate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6d32a-120">For apps that target the .NET Framework 4.6.2 or later, these changes are on  by default.</span></span> <span data-ttu-id="6d32a-121">Tali modifiche migliorano le prestazioni, consentendo al contempo ai metodi di accedere ai percorsi in precedenza inaccessibili.</span><span class="sxs-lookup"><span data-stu-id="6d32a-121">They should improve performance while allowing methods to access previously inaccessible paths.</span></span>  
  
<span data-ttu-id="6d32a-122">Le applicazioni destinate a .NET Framework 4.6.1 e versioni precedenti ma in esecuzione in .NET Framework 4.6.2 o versioni successive non sono interessate da questa modifica.</span><span class="sxs-lookup"><span data-stu-id="6d32a-122">Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="6d32a-123">Strategia di riduzione del rischio</span><span class="sxs-lookup"><span data-stu-id="6d32a-123">Mitigation</span></span>  
 <span data-ttu-id="6d32a-124">Le app destinate a .NET Framework 4.6.2 o versioni successive possono rifiutare esplicitamente questa modifica e usare la normalizzazione legacy aggiungendo quanto segue alla [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) sezione del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="6d32a-124">Apps that target the .NET Framework 4.6.2 or later can opt out of this change and use legacy normalization by adding the following to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
</runtime>  
```  
  
<span data-ttu-id="6d32a-125">Le app destinate a .NET Framework 4.6.1 o versioni precedenti ma in esecuzione nel .NET Framework 4.6.2 o versioni successive possono abilitare le modifiche alla normalizzazione del percorso aggiungendo la riga seguente alla [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) sezione del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="6d32a-125">Apps that target the .NET Framework 4.6.1 or earlier but are running on the .NET Framework 4.6.2 or later can enable the changes to path normalization by adding the following line to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application .configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6d32a-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d32a-126">See also</span></span>

- [<span data-ttu-id="6d32a-127">Compatibilità tra le versioni</span><span class="sxs-lookup"><span data-stu-id="6d32a-127">Application compatibility</span></span>](application-compatibility.md)
