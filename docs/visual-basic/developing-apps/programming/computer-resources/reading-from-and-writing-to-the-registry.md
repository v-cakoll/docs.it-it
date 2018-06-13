---
title: Lettura e scrittura nel Registro di sistema (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.Registry object, tasks
- registry [Visual Basic], writing to
- registry [Visual Basic], reading
ms.assetid: a13da106-185b-41d7-b23c-416da65e21e4
ms.openlocfilehash: 6ce05b956ebf9a544eb8c95165b0f709c694f334
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584618"
---
# <a name="reading-from-and-writing-to-the-registry-visual-basic"></a><span data-ttu-id="4d4e8-102">Lettura e scrittura nel Registro di sistema (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d4e8-102">Reading from and Writing to the Registry (Visual Basic)</span></span>
<span data-ttu-id="4d4e8-103">Questo argomento descrive attività e concetti correlati al Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="4d4e8-103">This topic describes task and conceptual topics that are associated with the registry.</span></span>  
  
 <span data-ttu-id="4d4e8-104">Durante la programmazione in Visual Basic è possibile scegliere di accedere al Registro di sistema usando le funzioni di Visual Basic o le classi del Registro di sistema di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d4e8-104">When programming in Visual Basic, you can choose to access the registry by means of either the functions provided by Visual Basic or the registry classes of the .NET Framework.</span></span> <span data-ttu-id="4d4e8-105">Il Registro di sistema contiene informazioni provenienti dal sistema operativo nonché informazioni provenienti dalle applicazioni presenti nel computer.</span><span class="sxs-lookup"><span data-stu-id="4d4e8-105">The registry hosts information from the operating system as well as information from applications hosted on the machine.</span></span> <span data-ttu-id="4d4e8-106">L'uso del Registro di sistema può compromettere la sicurezza poiché consente l'accesso inappropriato alle risorse di sistema o alle informazioni protette.</span><span class="sxs-lookup"><span data-stu-id="4d4e8-106">Working with the registry may compromise security by allowing inappropriate access to system resources or protected information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4d4e8-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="4d4e8-107">In This Section</span></span>  
 [<span data-ttu-id="4d4e8-108">Procedura: Creare una chiave del Registro di sistema e impostarne il valore</span><span class="sxs-lookup"><span data-stu-id="4d4e8-108">How to: Create a Registry Key and Set Its Value</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-create-a-registry-key-and-set-its-value.md)  
 <span data-ttu-id="4d4e8-109">Viene descritto come usare i metodi `CreateSubKey` e `SetValue` dell'oggetto `My.Computer.Registry` per creare una chiave del Registro di sistema e impostarne il valore.</span><span class="sxs-lookup"><span data-stu-id="4d4e8-109">Describes how to use the `CreateSubKey` and `SetValue` methods of the `My.Computer.Registry` object to create a registry key and set its value.</span></span>  
  
 [<span data-ttu-id="4d4e8-110">Procedura: Leggere un valore da una chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="4d4e8-110">How to: Read a Value from a Registry Key</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-read-a-value-from-a-registry-key.md)  
 <span data-ttu-id="4d4e8-111">Viene descritto come usare il metodo `GetValue` dell'oggetto `My.Computer.Registry` per leggere un valore da una chiave del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="4d4e8-111">Describes how to use the `GetValue` method of the `My.Computer.Registry` object to read a value from a registry key.</span></span>  
  
 [<span data-ttu-id="4d4e8-112">Procedura: Eliminare una chiave del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="4d4e8-112">How to: Delete a Registry Key</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-delete-a-registry-key.md)  
 <span data-ttu-id="4d4e8-113">Viene descritto come usare il metodo `DeleteSubKey` della proprietà `My.Computer.Registry.CurrentUser` per eliminare una chiave del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="4d4e8-113">Describes how to use the `DeleteSubKey` method of the `My.Computer.Registry.CurrentUser` property to delete a registry key.</span></span>  
  
 [<span data-ttu-id="4d4e8-114">Lettura e scrittura nel Registro di sistema mediante lo spazio dei nomi Microsoft.Win32</span><span class="sxs-lookup"><span data-stu-id="4d4e8-114">Reading from and Writing to the Registry Using the Microsoft.Win32 Namespace</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace.md)  
 <span data-ttu-id="4d4e8-115">Viene descritto come usare le classi `Registry` e `RegistryKey` di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] per accedere al Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="4d4e8-115">Describes how to use the `Registry` and `RegistryKey` classes of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] to access the registry.</span></span>  
  
 [<span data-ttu-id="4d4e8-116">Sicurezza e Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="4d4e8-116">Security and the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)  
 <span data-ttu-id="4d4e8-117">Vengono illustrati i problemi di sicurezza che riguardano il Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="4d4e8-117">Discusses security issues involving the registry.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4d4e8-118">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="4d4e8-118">Related Sections</span></span>  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 <span data-ttu-id="4d4e8-119">Vengono elencati e illustrati i membri dell'oggetto `My.Computer.Registry`.</span><span class="sxs-lookup"><span data-stu-id="4d4e8-119">Lists and explains members of the `My.Computer.Registry` object.</span></span>  
  
 <xref:Microsoft.Win32.Registry>  
 <span data-ttu-id="4d4e8-120">Viene presentata una panoramica della classe `Registry`, oltre a collegamenti a singoli membri e chiavi.</span><span class="sxs-lookup"><span data-stu-id="4d4e8-120">Presents an overview of the `Registry` class, along with links to individual keys and members.</span></span>
