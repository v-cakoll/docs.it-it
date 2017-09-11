---
title: Lettura e scrittura nel Registro di sistema mediante lo spazio dei nomi Microsoft.Win32 (Visual Basic)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- registry, Visual Basic
ms.assetid: 4a0dcce0-c27b-4199-baa8-ee4528da6a56
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cefde5317b2ed2bc0a2834224b1475e8020f7f25
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="reading-from-and-writing-to-the-registry-using-the-microsoftwin32-namespace-visual-basic"></a><span data-ttu-id="8e20e-102">Lettura e scrittura nel Registro di sistema mediante lo spazio dei nomi Microsoft.Win32 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e20e-102">Reading from and Writing to the Registry Using the Microsoft.Win32 Namespace (Visual Basic)</span></span>
<span data-ttu-id="8e20e-103">`My.Computer.Registry` dovrebbe essere in grado di soddisfare le esigenze di base della programmazione con il Registro di sistema, ma è possibile usare anche le classi <xref:Microsoft.Win32.Registry> e <xref:Microsoft.Win32.RegistryKey> dello spazio dei nomi <xref:Microsoft.Win32> di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8e20e-103">Although `My.Computer.Registry` should cover your basic needs when programming against the registry, you can also use the <xref:Microsoft.Win32.Registry> and <xref:Microsoft.Win32.RegistryKey> classes in the <xref:Microsoft.Win32> namespace of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="keys-in-the-registry-class"></a><span data-ttu-id="8e20e-104">Chiavi nella classe Registry</span><span class="sxs-lookup"><span data-stu-id="8e20e-104">Keys in the Registry Class</span></span>  
 <span data-ttu-id="8e20e-105">La classe <xref:Microsoft.Win32.Registry> include le chiavi di base del Registro di sistema che è possibile usare per accedere alle sottochiavi e ai relativi valori.</span><span class="sxs-lookup"><span data-stu-id="8e20e-105">The <xref:Microsoft.Win32.Registry> class supplies the base registry keys that can be used to access subkeys and their values.</span></span> <span data-ttu-id="8e20e-106">Le chiavi di base sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="8e20e-106">The base keys themselves are read-only.</span></span> <span data-ttu-id="8e20e-107">La tabella seguente elenca e descrive le sette chiavi esposte dalla classe <xref:Microsoft.Win32.Registry>.</span><span class="sxs-lookup"><span data-stu-id="8e20e-107">The following table lists and describes the seven keys exposed by the <xref:Microsoft.Win32.Registry> class.</span></span>  
  
|<span data-ttu-id="8e20e-108">**Key**</span><span class="sxs-lookup"><span data-stu-id="8e20e-108">**Key**</span></span>|<span data-ttu-id="8e20e-109">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="8e20e-109">**Description**</span></span>|  
|-------------|---------------------|  
|<xref:Microsoft.Win32.Registry.ClassesRoot>|<span data-ttu-id="8e20e-110">Definisce i tipi di documento e le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="8e20e-110">Defines the types of documents and the properties associated with those types.</span></span>|  
|<xref:Microsoft.Win32.Registry.CurrentConfig>|<span data-ttu-id="8e20e-111">Contiene informazioni non specifiche dell'utente sulla configurazione hardware.</span><span class="sxs-lookup"><span data-stu-id="8e20e-111">Contains hardware configuration information that is not user-specific.</span></span>|  
|<xref:Microsoft.Win32.Registry.CurrentUser>|<span data-ttu-id="8e20e-112">Contiene informazioni sulle preferenze dell'utente corrente, ad esempio le variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="8e20e-112">Contains information about the current user preferences, such as environmental variables.</span></span>|  
|<xref:Microsoft.Win32.Registry.DynData>|<span data-ttu-id="8e20e-113">Contiene i dati dinamici del Registro di sistema, ad esempio quelli usati dai driver delle periferiche virtuali.</span><span class="sxs-lookup"><span data-stu-id="8e20e-113">Contains dynamic registry data, such as that used by Virtual Device Drivers.</span></span>|  
|<xref:Microsoft.Win32.Registry.LocalMachine>|<span data-ttu-id="8e20e-114">Contiene cinque sottochiavi (Hardware, SAM, Security, Software e System) in cui sono disponibili i dati di configurazione relativi al computer locale.</span><span class="sxs-lookup"><span data-stu-id="8e20e-114">Contains five subkeys (Hardware, SAM, Security, Software, and System) that hold the configuration data for the local computer.</span></span>|  
|<xref:Microsoft.Win32.Registry.PerformanceData>|<span data-ttu-id="8e20e-115">Contiene informazioni sulle prestazioni per i componenti software.</span><span class="sxs-lookup"><span data-stu-id="8e20e-115">Contains performance information for software components.</span></span>|  
|<xref:Microsoft.Win32.Registry.Users>|<span data-ttu-id="8e20e-116">Contiene informazioni sulle preferenze predefinite degli utenti.</span><span class="sxs-lookup"><span data-stu-id="8e20e-116">Contains information about the default user preferences.</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="8e20e-117">È più sicuro scrivere dati per l'utente corrente (<xref:Microsoft.Win32.Registry.CurrentUser>) che non per il computer locale (<xref:Microsoft.Win32.Registry.LocalMachine>).</span><span class="sxs-lookup"><span data-stu-id="8e20e-117">It is more secure to write data to the current user (<xref:Microsoft.Win32.Registry.CurrentUser>) than to the local computer (<xref:Microsoft.Win32.Registry.LocalMachine>).</span></span> <span data-ttu-id="8e20e-118">Quando la chiave che si sta creando è stata precedentemente creata da un altro processo, probabilmente dannoso, si verifica una condizione comunemente definita "squatting".</span><span class="sxs-lookup"><span data-stu-id="8e20e-118">A condition that's typically referred to as "squatting" occurs when the key you are creating was previously created by another, possibly malicious, process.</span></span> <span data-ttu-id="8e20e-119">Per evitare che si verifichi tale situazione, usare un metodo, ad esempio <xref:Microsoft.Win32.RegistryKey.GetValue%2A>, che restituisce `Nothing` se la chiave non esiste già.</span><span class="sxs-lookup"><span data-stu-id="8e20e-119">To prevent this from occurring, use a method, such as <xref:Microsoft.Win32.RegistryKey.GetValue%2A>, that returns `Nothing` if the key does not already exist.</span></span>  
  
## <a name="reading-a-value-from-the-registry"></a><span data-ttu-id="8e20e-120">Lettura di un valore dal Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="8e20e-120">Reading a Value from the Registry</span></span>  
 <span data-ttu-id="8e20e-121">Il codice seguente illustra come leggere una stringa da HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="8e20e-121">The following code shows how to read a string from HKEY_CURRENT_USER.</span></span>  
  
 <span data-ttu-id="8e20e-122">[!code-vb[VbResourceTasks#20](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8e20e-122">[!code-vb[VbResourceTasks#20](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace_1.vb)]</span></span>  
  
 <span data-ttu-id="8e20e-123">Il codice seguente legge, incrementa e quindi scrive una stringa in HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="8e20e-123">The following code reads, increments, and then writes a string to HKEY_CURRENT_USER.</span></span>  
  
 <span data-ttu-id="8e20e-124">[!code-vb[VbResourceTasks#21](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8e20e-124">[!code-vb[VbResourceTasks#21](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e20e-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e20e-125">See Also</span></span>  
 <span data-ttu-id="8e20e-126"><xref:System.SystemException></span><span class="sxs-lookup"><span data-stu-id="8e20e-126"><xref:System.SystemException></span></span>   
 <span data-ttu-id="8e20e-127"><xref:System.ApplicationException></span><span class="sxs-lookup"><span data-stu-id="8e20e-127"><xref:System.ApplicationException></span></span>   
 <span data-ttu-id="8e20e-128"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy></span><span class="sxs-lookup"><span data-stu-id="8e20e-128"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy></span></span>   
 <span data-ttu-id="8e20e-129">[Istruzione Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8e20e-129">[Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) </span></span>  
 <span data-ttu-id="8e20e-130">[Lettura e scrittura nel Registro di sistema](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span><span class="sxs-lookup"><span data-stu-id="8e20e-130">[Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span></span>  
 [<span data-ttu-id="8e20e-131">Sicurezza e Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="8e20e-131">Security and the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)

