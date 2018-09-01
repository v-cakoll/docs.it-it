---
title: Accesso alle risorse del computer (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- computer resources [Visual Basic]
- My.Computer object [Visual Basic], tasks
- computer resources [Visual Basic], accessing
ms.assetid: 75b81c88-f7c0-46e0-95c8-0c006d2120f9
ms.openlocfilehash: 7128a71f28d1755a14fcda5f09bee11202ab4154
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43422464"
---
# <a name="accessing-computer-resources-visual-basic"></a><span data-ttu-id="a8f43-102">Accesso alle risorse del computer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8f43-102">Accessing computer resources (Visual Basic)</span></span>

<span data-ttu-id="a8f43-103">L'oggetto `My.Computer` è uno dei tre oggetti principali di `My` e permette l'accesso a informazioni e funzionalità usate di frequente.</span><span class="sxs-lookup"><span data-stu-id="a8f43-103">The `My.Computer` object is one of the three central objects in `My`, providing access to information and commonly used functionality.</span></span> <span data-ttu-id="a8f43-104">`My.Computer` specifica metodi, proprietà ed eventi per l'accesso al computer in cui è eseguita l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a8f43-104">`My.Computer` provides methods, properties, and events for accessing the computer on which the application is running.</span></span> <span data-ttu-id="a8f43-105">Gli oggetti includono:</span><span class="sxs-lookup"><span data-stu-id="a8f43-105">Its objects include:</span></span>  
  
-   <xref:Microsoft.VisualBasic.Devices.Audio>
-   <span data-ttu-id="a8f43-106">Appunti (<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>)</span><span class="sxs-lookup"><span data-stu-id="a8f43-106">Clipboard (<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>)</span></span>
-   <xref:Microsoft.VisualBasic.Devices.Clock>
-   <xref:Microsoft.VisualBasic.FileIO.FileSystem>
-   <xref:Microsoft.VisualBasic.Devices.ServerComputer.Info%2A>
-   <xref:Microsoft.VisualBasic.Devices.Keyboard>
-   <xref:Microsoft.VisualBasic.Devices.Mouse>
-   <xref:Microsoft.VisualBasic.Devices.Network>
-   <xref:Microsoft.VisualBasic.Devices.Ports>
-   <span data-ttu-id="a8f43-107">Registro di sistema (<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>)</span><span class="sxs-lookup"><span data-stu-id="a8f43-107">Registry (<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>)</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="a8f43-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a8f43-108">In this section</span></span>

<span data-ttu-id="a8f43-109">[Riproduzione di suoni](../../../../visual-basic/developing-apps/programming/computer-resources/playing-sounds.md) </span><span class="sxs-lookup"><span data-stu-id="a8f43-109">[Playing Sounds](../../../../visual-basic/developing-apps/programming/computer-resources/playing-sounds.md) </span></span>  
<span data-ttu-id="a8f43-110">Elenca le attività associate a `My.Computer.Audio`, ad esempio la riproduzione di un suono in background.</span><span class="sxs-lookup"><span data-stu-id="a8f43-110">Lists tasks associated with `My.Computer.Audio`, such as playing a sound in the background.</span></span>

<span data-ttu-id="a8f43-111">[Archiviazione e lettura di dati negli Appunti](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md) </span><span class="sxs-lookup"><span data-stu-id="a8f43-111">[Storing Data to and Reading from the Clipboard](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md) </span></span>  
<span data-ttu-id="a8f43-112">Elenca le attività associate a `My.Computer.Clipboard`, ad esempio la lettura o la scrittura di dati negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="a8f43-112">Lists tasks associated with `My.Computer.Clipboard`, such as reading data from or writing data to the Clipboard.</span></span>

<span data-ttu-id="a8f43-113">[Ottenere informazioni sul computer](../../../../visual-basic/developing-apps/programming/computer-resources/getting-information-about-the-computer.md) </span><span class="sxs-lookup"><span data-stu-id="a8f43-113">[Getting Information about the Computer](../../../../visual-basic/developing-apps/programming/computer-resources/getting-information-about-the-computer.md) </span></span>  
<span data-ttu-id="a8f43-114">Elenca le attività associate a `My.Computer.Info`, ad esempio il rilevamento del nome completo di un computer o di indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="a8f43-114">Lists tasks associated with `My.Computer.Info`, such as determining a computer's full name or IP addresses.</span></span>

<span data-ttu-id="a8f43-115">[Accesso alla tastiera](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md) </span><span class="sxs-lookup"><span data-stu-id="a8f43-115">[Accessing the Keyboard](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-keyboard.md) </span></span>  
<span data-ttu-id="a8f43-116">Elenca le attività associate a `My.Computer.Keyboard`, ad esempio il rilevamento di BLOC MAIUSC attivo.</span><span class="sxs-lookup"><span data-stu-id="a8f43-116">Lists tasks associated with `My.Computer.Keyboard`, such as determining whether CAPS LOCK is on.</span></span>

<span data-ttu-id="a8f43-117">[Accesso al mouse](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-mouse.md) </span><span class="sxs-lookup"><span data-stu-id="a8f43-117">[Accessing the Mouse](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-mouse.md) </span></span>  
<span data-ttu-id="a8f43-118">Elenca le attività associate a `My.Computer.Mouse`, ad esempio il rilevamento della presenza di un mouse.</span><span class="sxs-lookup"><span data-stu-id="a8f43-118">Lists tasks associated with `My.Computer.Mouse`, such as determining whether a mouse is present.</span></span>

<span data-ttu-id="a8f43-119">[Esecuzione di operazioni di rete](../../../../visual-basic/developing-apps/programming/computer-resources/performing-network-operations.md) </span><span class="sxs-lookup"><span data-stu-id="a8f43-119">[Performing Network Operations](../../../../visual-basic/developing-apps/programming/computer-resources/performing-network-operations.md) </span></span>  
<span data-ttu-id="a8f43-120">Elenca le attività associate a `My.Computer.Network`, ad esempio il caricamento o il download di file.</span><span class="sxs-lookup"><span data-stu-id="a8f43-120">Lists tasks associated with `My.Computer.Network`, such as uploading or downloading files.</span></span>

<span data-ttu-id="a8f43-121">[Accesso alle porte del computer](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md) </span><span class="sxs-lookup"><span data-stu-id="a8f43-121">[Accessing the Computer's Ports](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md) </span></span>  
<span data-ttu-id="a8f43-122">Elenca le attività associate a `My.Computer.Ports`, ad esempio la visualizzazione delle porte seriali disponibili o l'invio di stringhe a porte seriali.</span><span class="sxs-lookup"><span data-stu-id="a8f43-122">Lists tasks associated with `My.Computer.Ports`, such as showing available serial ports or sending strings to serial ports.</span></span>

<span data-ttu-id="a8f43-123">[Lettura e scrittura nel Registro di sistema](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span><span class="sxs-lookup"><span data-stu-id="a8f43-123">[Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span></span>  
<span data-ttu-id="a8f43-124">Elenca le attività associate a `My.Computer.Registry`, ad esempio la lettura o la scrittura di dati nelle chiavi del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="a8f43-124">Lists tasks associated with `My.Computer.Registry`, such as reading data from or writing data to registry keys.</span></span>
