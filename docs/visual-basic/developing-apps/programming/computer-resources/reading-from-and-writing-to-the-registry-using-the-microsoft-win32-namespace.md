---
title: Lettura e scrittura nel Registro di sistema mediante lo spazio dei nomi Microsoft.Win32
ms.date: 07/20/2015
helpviewer_keywords:
- registry [Visual Basic]
ms.assetid: 4a0dcce0-c27b-4199-baa8-ee4528da6a56
ms.openlocfilehash: 841344186b8e56717b81e90397aabc608bdc6dab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345494"
---
# <a name="reading-from-and-writing-to-the-registry-using-the-microsoftwin32-namespace-visual-basic"></a><span data-ttu-id="827f5-102">Lettura e scrittura nel Registro di sistema mediante lo spazio dei nomi Microsoft.Win32 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="827f5-102">Reading from and Writing to the Registry Using the Microsoft.Win32 Namespace (Visual Basic)</span></span>

<span data-ttu-id="827f5-103">`My.Computer.Registry` dovrebbe essere in grado di soddisfare le esigenze di base della programmazione con il Registro di sistema, ma è possibile usare anche le classi <xref:Microsoft.Win32.Registry> e <xref:Microsoft.Win32.RegistryKey> dello spazio dei nomi <xref:Microsoft.Win32> di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="827f5-103">Although `My.Computer.Registry` should cover your basic needs when programming against the registry, you can also use the <xref:Microsoft.Win32.Registry> and <xref:Microsoft.Win32.RegistryKey> classes in the <xref:Microsoft.Win32> namespace of the .NET Framework.</span></span>  
  
## <a name="keys-in-the-registry-class"></a><span data-ttu-id="827f5-104">Chiavi nella classe Registry</span><span class="sxs-lookup"><span data-stu-id="827f5-104">Keys in the Registry Class</span></span>  

 <span data-ttu-id="827f5-105">La classe <xref:Microsoft.Win32.Registry> include le chiavi di base del Registro di sistema che è possibile usare per accedere alle sottochiavi e ai relativi valori.</span><span class="sxs-lookup"><span data-stu-id="827f5-105">The <xref:Microsoft.Win32.Registry> class supplies the base registry keys that can be used to access subkeys and their values.</span></span> <span data-ttu-id="827f5-106">Le chiavi di base sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="827f5-106">The base keys themselves are read-only.</span></span> <span data-ttu-id="827f5-107">La tabella seguente elenca e descrive le sette chiavi esposte dalla classe <xref:Microsoft.Win32.Registry>.</span><span class="sxs-lookup"><span data-stu-id="827f5-107">The following table lists and describes the seven keys exposed by the <xref:Microsoft.Win32.Registry> class.</span></span>  
  
|<span data-ttu-id="827f5-108">**Codice**</span><span class="sxs-lookup"><span data-stu-id="827f5-108">**Key**</span></span>|<span data-ttu-id="827f5-109">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="827f5-109">**Description**</span></span>|  
|-------------|---------------------|  
|<xref:Microsoft.Win32.Registry.ClassesRoot>|<span data-ttu-id="827f5-110">Definisce i tipi di documento e le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="827f5-110">Defines the types of documents and the properties associated with those types.</span></span>|  
|<xref:Microsoft.Win32.Registry.CurrentConfig>|<span data-ttu-id="827f5-111">Contiene informazioni non specifiche dell'utente sulla configurazione hardware.</span><span class="sxs-lookup"><span data-stu-id="827f5-111">Contains hardware configuration information that is not user-specific.</span></span>|  
|<xref:Microsoft.Win32.Registry.CurrentUser>|<span data-ttu-id="827f5-112">Contiene informazioni sulle preferenze dell'utente corrente, ad esempio le variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="827f5-112">Contains information about the current user preferences, such as environmental variables.</span></span>|  
|<xref:Microsoft.Win32.Registry.DynData>|<span data-ttu-id="827f5-113">Contiene i dati dinamici del Registro di sistema, ad esempio quelli usati dai driver delle periferiche virtuali.</span><span class="sxs-lookup"><span data-stu-id="827f5-113">Contains dynamic registry data, such as that used by Virtual Device Drivers.</span></span>|  
|<xref:Microsoft.Win32.Registry.LocalMachine>|<span data-ttu-id="827f5-114">Contiene cinque sottochiavi (Hardware, SAM, Security, Software e System) in cui sono disponibili i dati di configurazione relativi al computer locale.</span><span class="sxs-lookup"><span data-stu-id="827f5-114">Contains five subkeys (Hardware, SAM, Security, Software, and System) that hold the configuration data for the local computer.</span></span>|  
|<xref:Microsoft.Win32.Registry.PerformanceData>|<span data-ttu-id="827f5-115">Contiene informazioni sulle prestazioni per i componenti software.</span><span class="sxs-lookup"><span data-stu-id="827f5-115">Contains performance information for software components.</span></span>|  
|<xref:Microsoft.Win32.Registry.Users>|<span data-ttu-id="827f5-116">Contiene informazioni sulle preferenze predefinite degli utenti.</span><span class="sxs-lookup"><span data-stu-id="827f5-116">Contains information about the default user preferences.</span></span>|  
  
> [!IMPORTANT]
> <span data-ttu-id="827f5-117">È più sicuro scrivere dati per l'utente corrente (<xref:Microsoft.Win32.Registry.CurrentUser>) che non per il computer locale (<xref:Microsoft.Win32.Registry.LocalMachine>).</span><span class="sxs-lookup"><span data-stu-id="827f5-117">It is more secure to write data to the current user (<xref:Microsoft.Win32.Registry.CurrentUser>) than to the local computer (<xref:Microsoft.Win32.Registry.LocalMachine>).</span></span> <span data-ttu-id="827f5-118">Quando la chiave che si sta creando è stata precedentemente creata da un altro processo, probabilmente dannoso, si verifica una condizione comunemente definita "squatting".</span><span class="sxs-lookup"><span data-stu-id="827f5-118">A condition that's typically referred to as "squatting" occurs when the key you are creating was previously created by another, possibly malicious, process.</span></span> <span data-ttu-id="827f5-119">Per evitare che si verifichi tale situazione, usare un metodo, ad esempio <xref:Microsoft.Win32.RegistryKey.GetValue%2A>, che restituisce `Nothing` se la chiave non esiste già.</span><span class="sxs-lookup"><span data-stu-id="827f5-119">To prevent this from occurring, use a method, such as <xref:Microsoft.Win32.RegistryKey.GetValue%2A>, that returns `Nothing` if the key does not already exist.</span></span>  
  
## <a name="reading-a-value-from-the-registry"></a><span data-ttu-id="827f5-120">Lettura di un valore dal Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="827f5-120">Reading a Value from the Registry</span></span>  

 <span data-ttu-id="827f5-121">Il codice seguente illustra come leggere una stringa da HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="827f5-121">The following code shows how to read a string from HKEY_CURRENT_USER.</span></span>  
  
 [!code-vb[VbResourceTasks#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#20)]  
  
 <span data-ttu-id="827f5-122">Il codice seguente legge, incrementa e quindi scrive una stringa in HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="827f5-122">The following code reads, increments, and then writes a string to HKEY_CURRENT_USER.</span></span>  
  
 [!code-vb[VbResourceTasks#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="827f5-123">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="827f5-123">See also</span></span>

- <xref:System.SystemException>
- <xref:System.ApplicationException>
- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- [<span data-ttu-id="827f5-124">Istruzione Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="827f5-124">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="827f5-125">Lettura e scrittura nel Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="827f5-125">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
- [<span data-ttu-id="827f5-126">Sicurezza e Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="827f5-126">Security and the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)
