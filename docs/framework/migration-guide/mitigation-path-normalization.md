---
title: 'Migrazione: Normalizzazione del percorso'
ms.date: 03/30/2017
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
ms.openlocfilehash: 61c8eec2043aa2fb9309ee6052e27fc2c91c6c6a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181228"
---
# <a name="mitigation-path-normalization"></a><span data-ttu-id="5445e-102">Migrazione: Normalizzazione del percorso</span><span class="sxs-lookup"><span data-stu-id="5445e-102">Mitigation: Path Normalization</span></span>
<span data-ttu-id="5445e-103">A partire dalle applicazioni destinate a .NET Framework 4.6.2, la normalizzazione del percorso in .NET Framework è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="5445e-103">Starting with apps the target  the .NET Framework 4.6.2, path normalization in the .NET Framework has changed.</span></span>  
  
## <a name="what-is-path-normalization"></a><span data-ttu-id="5445e-104">Che cos'è la normalizzazione di un percorso?</span><span class="sxs-lookup"><span data-stu-id="5445e-104">What is path normalization?</span></span>  
 <span data-ttu-id="5445e-105">La normalizzazione di un percorso include la modifica della stringa che identifica un file o il percorso in modo che sia conforme a un percorso valido sul sistema operativo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5445e-105">Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="5445e-106">In genere, la normalizzazione implica:</span><span class="sxs-lookup"><span data-stu-id="5445e-106">Normalization typically involves:</span></span>  
  
- <span data-ttu-id="5445e-107">La conversione in forma canonica dei separatori di directory e dei componenti.</span><span class="sxs-lookup"><span data-stu-id="5445e-107">Canonicalizing component and directory separators.</span></span>  
  
- <span data-ttu-id="5445e-108">L'applicazione della directory corrente in un percorso relativo.</span><span class="sxs-lookup"><span data-stu-id="5445e-108">Applying the current directory to a relative path.</span></span>  
  
- <span data-ttu-id="5445e-109">La valutazione della directory relativa (`.`) o della directory padre (`..`) in un percorso.</span><span class="sxs-lookup"><span data-stu-id="5445e-109">Evaluating the relative directory (`.`) or the parent directory (`..`) in a path.</span></span>  
  
- <span data-ttu-id="5445e-110">La rimozione di caratteri specificati.</span><span class="sxs-lookup"><span data-stu-id="5445e-110">Trimming specified characters.</span></span>  
  
## <a name="the-changes"></a><span data-ttu-id="5445e-111">Le modifiche</span><span class="sxs-lookup"><span data-stu-id="5445e-111">The changes</span></span>  
 <span data-ttu-id="5445e-112">A partire dalle applicazioni destinate a .NET Framework 4.6.2, la normalizzazione del percorso è stata modificata come segue:</span><span class="sxs-lookup"><span data-stu-id="5445e-112">Starting with apps that target the .NET Framework 4.6.2, path normalization has changed in the following ways:</span></span>  
  
- <span data-ttu-id="5445e-113">Il runtime viene rinviato alla funzione [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) del sistema operativo per normalizzare i percorsi.</span><span class="sxs-lookup"><span data-stu-id="5445e-113">The runtime defers to the operating system's [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) function to normalize paths.</span></span>  
  
- <span data-ttu-id="5445e-114">La normalizzazione non consiste più nel rimuovere la fine dei segmenti di directory (ad esempio uno spazio alla fine di un nome di directory).</span><span class="sxs-lookup"><span data-stu-id="5445e-114">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>  
  
- <span data-ttu-id="5445e-115">Supporto per la sintassi del percorso dispositivo in attendibilità totale, tra cui `\\.\` e, per le API del file I/O in mscorlib. dll, `\\?\`.</span><span class="sxs-lookup"><span data-stu-id="5445e-115">Support for device path syntax in full trust, including  `\\.\` and, for file I/O APIs   in mscorlib.dll, `\\?\`.</span></span>  
  
- <span data-ttu-id="5445e-116">Il runtime non convalida i percorsi di sintassi del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5445e-116">The runtime does not validate device syntax paths.</span></span>  
  
- <span data-ttu-id="5445e-117">È supportato l'uso della sintassi del dispositivo per accedere ai flussi di dati alternativi.</span><span class="sxs-lookup"><span data-stu-id="5445e-117">The use of device syntax to access alternate data streams is supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="5445e-118">Impatto</span><span class="sxs-lookup"><span data-stu-id="5445e-118">Impact</span></span>  

<span data-ttu-id="5445e-119">Per le applicazioni destinate a .NET Framework 4.6.2 o versioni successive, queste modifiche sono applicate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5445e-119">For apps that target the .NET Framework 4.6.2 or later, these changes are on  by default.</span></span> <span data-ttu-id="5445e-120">Tali modifiche migliorano le prestazioni, consentendo al contempo ai metodi di accedere ai percorsi in precedenza inaccessibili.</span><span class="sxs-lookup"><span data-stu-id="5445e-120">They should improve performance while allowing methods to access previously inaccessible paths.</span></span>  
  
<span data-ttu-id="5445e-121">Le applicazioni destinate a .NET Framework 4.6.1 e versioni precedenti ma in esecuzione in .NET Framework 4.6.2 o versioni successive non sono interessate da questa modifica.</span><span class="sxs-lookup"><span data-stu-id="5445e-121">Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="5445e-122">Strategia di riduzione del rischio</span><span class="sxs-lookup"><span data-stu-id="5445e-122">Mitigation</span></span>  
 <span data-ttu-id="5445e-123">Le app destinate a .NET Framework 4.6.2 o versioni successive possono rifiutare esplicitamente questa modifica e usare la normalizzazione legacy aggiungendo quanto segue alla sezione [ \<di>](../configure-apps/file-schema/runtime/runtime-element.md) di runtime del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="5445e-123">Apps that target the .NET Framework 4.6.2 or later can opt out of this change and use legacy normalization by adding the following to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
</runtime>  
```  
  
<span data-ttu-id="5445e-124">Le app destinate a .NET Framework 4.6.1 o versioni precedenti ma in esecuzione in .NET Framework 4.6.2 o versioni successive possono abilitare le modifiche alla normalizzazione del percorso aggiungendo la riga seguente alla sezione>di [ \<runtime](../configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="5445e-124">Apps that target the .NET Framework 4.6.1 or earlier but are running on the .NET Framework 4.6.2 or later can enable the changes to path normalization by adding the following line to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application .configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5445e-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5445e-125">See also</span></span>

- [<span data-ttu-id="5445e-126">Compatibilità tra le versioni</span><span class="sxs-lookup"><span data-stu-id="5445e-126">Application compatibility</span></span>](application-compatibility.md)
