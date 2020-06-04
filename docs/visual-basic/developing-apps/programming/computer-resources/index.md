---
title: Accesso alle risorse del computer
ms.date: 07/20/2015
helpviewer_keywords:
- computer resources [Visual Basic]
- My.Computer object [Visual Basic], tasks
- computer resources [Visual Basic], accessing
ms.assetid: 75b81c88-f7c0-46e0-95c8-0c006d2120f9
ms.openlocfilehash: 9595abaa1daa2b4a4436577d58856183dcb4d9ac
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401784"
---
# <a name="accessing-computer-resources-visual-basic"></a><span data-ttu-id="0c348-102">Accesso alle risorse del computer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c348-102">Accessing computer resources (Visual Basic)</span></span>

<span data-ttu-id="0c348-103">L'oggetto `My.Computer` è uno dei tre oggetti principali di `My` e permette l'accesso a informazioni e funzionalità usate di frequente.</span><span class="sxs-lookup"><span data-stu-id="0c348-103">The `My.Computer` object is one of the three central objects in `My`, providing access to information and commonly used functionality.</span></span> <span data-ttu-id="0c348-104">`My.Computer` specifica metodi, proprietà ed eventi per l'accesso al computer in cui è eseguita l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0c348-104">`My.Computer` provides methods, properties, and events for accessing the computer on which the application is running.</span></span> <span data-ttu-id="0c348-105">Gli oggetti includono:</span><span class="sxs-lookup"><span data-stu-id="0c348-105">Its objects include:</span></span>

- <xref:Microsoft.VisualBasic.Devices.Audio>
- <span data-ttu-id="0c348-106">Appunti (<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>)</span><span class="sxs-lookup"><span data-stu-id="0c348-106">Clipboard (<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>)</span></span>
- <xref:Microsoft.VisualBasic.Devices.Clock>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.Devices.ServerComputer.Info%2A>
- <xref:Microsoft.VisualBasic.Devices.Keyboard>
- <xref:Microsoft.VisualBasic.Devices.Mouse>
- <xref:Microsoft.VisualBasic.Devices.Network>
- <xref:Microsoft.VisualBasic.Devices.Ports>
- <span data-ttu-id="0c348-107">Registro di sistema (<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>)</span><span class="sxs-lookup"><span data-stu-id="0c348-107">Registry (<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>)</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0c348-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0c348-108">In this section</span></span>

[<span data-ttu-id="0c348-109">Riproduzione di suoni</span><span class="sxs-lookup"><span data-stu-id="0c348-109">Playing Sounds</span></span>](playing-sounds.md)  
<span data-ttu-id="0c348-110">Elenca le attività associate a `My.Computer.Audio`, ad esempio la riproduzione di un suono in background.</span><span class="sxs-lookup"><span data-stu-id="0c348-110">Lists tasks associated with `My.Computer.Audio`, such as playing a sound in the background.</span></span>

[<span data-ttu-id="0c348-111">Archiviazione e lettura di dati negli Appunti</span><span class="sxs-lookup"><span data-stu-id="0c348-111">Storing Data to and Reading from the Clipboard</span></span>](storing-data-to-and-reading-from-the-clipboard.md)  
<span data-ttu-id="0c348-112">Elenca le attività associate a `My.Computer.Clipboard`, ad esempio la lettura o la scrittura di dati negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="0c348-112">Lists tasks associated with `My.Computer.Clipboard`, such as reading data from or writing data to the Clipboard.</span></span>

[<span data-ttu-id="0c348-113">Ottenere informazioni sul computer</span><span class="sxs-lookup"><span data-stu-id="0c348-113">Getting Information about the Computer</span></span>](getting-information-about-the-computer.md)  
<span data-ttu-id="0c348-114">Elenca le attività associate a `My.Computer.Info`, ad esempio il rilevamento del nome completo di un computer o di indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="0c348-114">Lists tasks associated with `My.Computer.Info`, such as determining a computer's full name or IP addresses.</span></span>

[<span data-ttu-id="0c348-115">Accesso alla tastiera</span><span class="sxs-lookup"><span data-stu-id="0c348-115">Accessing the Keyboard</span></span>](accessing-the-keyboard.md)  
<span data-ttu-id="0c348-116">Elenca le attività associate a `My.Computer.Keyboard`, ad esempio il rilevamento di BLOC MAIUSC attivo.</span><span class="sxs-lookup"><span data-stu-id="0c348-116">Lists tasks associated with `My.Computer.Keyboard`, such as determining whether CAPS LOCK is on.</span></span>

[<span data-ttu-id="0c348-117">Accesso al mouse</span><span class="sxs-lookup"><span data-stu-id="0c348-117">Accessing the Mouse</span></span>](accessing-the-mouse.md)  
<span data-ttu-id="0c348-118">Elenca le attività associate a `My.Computer.Mouse`, ad esempio il rilevamento della presenza di un mouse.</span><span class="sxs-lookup"><span data-stu-id="0c348-118">Lists tasks associated with `My.Computer.Mouse`, such as determining whether a mouse is present.</span></span>

[<span data-ttu-id="0c348-119">Esecuzione di operazioni di rete</span><span class="sxs-lookup"><span data-stu-id="0c348-119">Performing Network Operations</span></span>](performing-network-operations.md)  
<span data-ttu-id="0c348-120">Elenca le attività associate a `My.Computer.Network`, ad esempio il caricamento o il download di file.</span><span class="sxs-lookup"><span data-stu-id="0c348-120">Lists tasks associated with `My.Computer.Network`, such as uploading or downloading files.</span></span>

[<span data-ttu-id="0c348-121">Accesso alle porte del computer</span><span class="sxs-lookup"><span data-stu-id="0c348-121">Accessing the Computer's Ports</span></span>](accessing-the-computer-s-ports.md)  
<span data-ttu-id="0c348-122">Elenca le attività associate a `My.Computer.Ports`, ad esempio la visualizzazione delle porte seriali disponibili o l'invio di stringhe a porte seriali.</span><span class="sxs-lookup"><span data-stu-id="0c348-122">Lists tasks associated with `My.Computer.Ports`, such as showing available serial ports or sending strings to serial ports.</span></span>

[<span data-ttu-id="0c348-123">Lettura e scrittura nel Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="0c348-123">Reading from and Writing to the Registry</span></span>](reading-from-and-writing-to-the-registry.md)  
<span data-ttu-id="0c348-124">Elenca le attività associate a `My.Computer.Registry`, ad esempio la lettura o la scrittura di dati nelle chiavi del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="0c348-124">Lists tasks associated with `My.Computer.Registry`, such as reading data from or writing data to registry keys.</span></span>
