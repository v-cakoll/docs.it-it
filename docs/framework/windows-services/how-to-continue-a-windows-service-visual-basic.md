---
title: 'Procedura: Continuare un servizio Windows (Visual Basic)'
description: Informazioni su come usare il componente ServiceController per continuare un servizio Windows, ad esempio il servizio di amministrazione di IIS, in un computer locale con Visual Basic.
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Continue
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
author: ghogen
ms.openlocfilehash: 2a04e330ea7dc37552053b2a7915909c011727f8
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925787"
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a><span data-ttu-id="ff915-103">Procedura: Continuare un servizio Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff915-103">How to: Continue a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="ff915-104">Questo esempio usa il componente <xref:System.ServiceProcess.ServiceController> per continuare l'esecuzione del servizio IIS Admin nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="ff915-104">This example uses the <xref:System.ServiceProcess.ServiceController> component to continue the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff915-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="ff915-105">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 <span data-ttu-id="ff915-106">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="ff915-106">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="ff915-107">Nello strumento di selezione dei frammenti di codice il frammento si trova in **Sistema operativo Windows > Servizi Windows**.</span><span class="sxs-lookup"><span data-stu-id="ff915-107">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="ff915-108">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="ff915-108">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ff915-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ff915-109">Compiling the Code</span></span>  
 <span data-ttu-id="ff915-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ff915-110">This example requires:</span></span>  
  
- <span data-ttu-id="ff915-111">Un riferimento del progetto a System.serviceprocess.dll.</span><span class="sxs-lookup"><span data-stu-id="ff915-111">A project reference to System.serviceprocess.dll.</span></span>  
  
- <span data-ttu-id="ff915-112">Accedere ai membri dello spazio dei nomi <xref:System.ServiceProcess>.</span><span class="sxs-lookup"><span data-stu-id="ff915-112">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="ff915-113">Aggiungere un'istruzione `Imports` se i nomi dei membri all'interno del codice non sono specificati in modo completo.</span><span class="sxs-lookup"><span data-stu-id="ff915-113">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="ff915-114">Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="ff915-114">For more information, see [Imports Statement (.NET Namespace and Type)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ff915-115">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="ff915-115">Robust Programming</span></span>  
 <span data-ttu-id="ff915-116">La proprietà <xref:System.ServiceProcess.ServiceController.MachineName%2A> della classe <xref:System.ServiceProcess.ServiceController> è il computer locale per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ff915-116">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="ff915-117">Per fare riferimento a servizi di Windows in un altro computer, modificare la proprietà <xref:System.ServiceProcess.ServiceController.MachineName%2A> impostando il nome di tale computer.</span><span class="sxs-lookup"><span data-stu-id="ff915-117">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="ff915-118">Non è possibile chiamare il metodo <xref:System.ServiceProcess.ServiceController.Continue%2A> su un servizio fino a quando lo stato del controller del servizio è <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.</span><span class="sxs-lookup"><span data-stu-id="ff915-118">You cannot call the <xref:System.ServiceProcess.ServiceController.Continue%2A> method on a service until the service controller status is <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.</span></span>  
  
 <span data-ttu-id="ff915-119">Le seguenti condizioni possono generare un'eccezione:</span><span class="sxs-lookup"><span data-stu-id="ff915-119">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="ff915-120">Non è possibile riprendere il servizio.</span><span class="sxs-lookup"><span data-stu-id="ff915-120">The service cannot be resumed.</span></span> <span data-ttu-id="ff915-121">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="ff915-121">(<xref:System.InvalidOperationException>)</span></span>  
  
- <span data-ttu-id="ff915-122">Si è verificato un errore durante l'accesso a un'API di sistema.</span><span class="sxs-lookup"><span data-stu-id="ff915-122">An error occurred when accessing a system API.</span></span> <span data-ttu-id="ff915-123">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="ff915-123">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ff915-124">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ff915-124">.NET Framework Security</span></span>  
 <span data-ttu-id="ff915-125">Il controllo dei servizi nel computer può essere limitato tramite l'enumerazione <xref:System.ServiceProcess.ServiceControllerPermissionAccess> per impostare le autorizzazioni nella classe <xref:System.ServiceProcess.ServiceControllerPermission>.</span><span class="sxs-lookup"><span data-stu-id="ff915-125">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> enumeration to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission> class.</span></span>  
  
 <span data-ttu-id="ff915-126">L'accesso alle informazioni sul servizio può essere limitato tramite l'enumerazione <xref:System.Security.Permissions.PermissionState> per impostare le autorizzazioni nella classe <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="ff915-126">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> enumeration to set permissions in the <xref:System.Security.Permissions.SecurityPermission> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff915-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff915-127">See also</span></span>

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- [<span data-ttu-id="ff915-128">Procedura: Sospendere un servizio Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff915-128">How to: Pause a Windows Service (Visual Basic)</span></span>](how-to-pause-a-windows-service-visual-basic.md)
