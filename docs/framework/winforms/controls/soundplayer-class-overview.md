---
title: Cenni preliminari sulla classe SoundPlayer
ms.date: 03/30/2017
helpviewer_keywords:
- playing sounds [Windows Forms], SoundPlayer class
- SoundPlayer class [Windows Forms], about SoundPlayer class
- sounds [Windows Forms], playing
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
ms.openlocfilehash: 3ff23cbfa78b803d4526e7a7c389fd5d458a967c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972003"
---
# <a name="soundplayer-class-overview"></a><span data-ttu-id="20d91-102">Cenni preliminari sulla classe SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="20d91-102">SoundPlayer Class Overview</span></span>
<span data-ttu-id="20d91-103">La classe <xref:System.Media.SoundPlayer> consente di includere facilmente suoni nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="20d91-103">The <xref:System.Media.SoundPlayer> class enables you to easily include sounds in your applications.</span></span>  
  
 <span data-ttu-id="20d91-104">Il <xref:System.Media.SoundPlayer> classe consente di riprodurre file audio in formato WAV, da una risorsa o da percorsi UNC o HTTP.</span><span class="sxs-lookup"><span data-stu-id="20d91-104">The <xref:System.Media.SoundPlayer> class can play sound files in the .wav format, either from a resource or from UNC or HTTP locations.</span></span> <span data-ttu-id="20d91-105">Inoltre, il <xref:System.Media.SoundPlayer> classe consente di caricare o riprodurre suoni in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="20d91-105">Additionally, the <xref:System.Media.SoundPlayer> class enables you to load or play sounds asynchronously.</span></span>  
  
 <span data-ttu-id="20d91-106">È anche possibile usare la classe<xref:System.Media.SystemSounds> per riprodurre suoni del sistema comuni, compresi i segnali acustici.</span><span class="sxs-lookup"><span data-stu-id="20d91-106">You can also use the <xref:System.Media.SystemSounds> class to play common system sounds, including a beep.</span></span>  
  
## <a name="commonly-used-properties-methods-and-events"></a><span data-ttu-id="20d91-107">Proprietà, metodi ed eventi usati comunemente</span><span class="sxs-lookup"><span data-stu-id="20d91-107">Commonly Used Properties, Methods, and Events</span></span>  
  
|<span data-ttu-id="20d91-108">Nome</span><span class="sxs-lookup"><span data-stu-id="20d91-108">Name</span></span>|<span data-ttu-id="20d91-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20d91-109">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="20d91-110">Proprietà <xref:System.Media.SoundPlayer.SoundLocation%2A></span><span class="sxs-lookup"><span data-stu-id="20d91-110"><xref:System.Media.SoundPlayer.SoundLocation%2A> property</span></span>|<span data-ttu-id="20d91-111">Percorso del file o l'indirizzo Web del suono.</span><span class="sxs-lookup"><span data-stu-id="20d91-111">The file path or Web address of the sound.</span></span> <span data-ttu-id="20d91-112">I valori accettabili sono UNC o HTTP.</span><span class="sxs-lookup"><span data-stu-id="20d91-112">Acceptable values can be UNC or HTTP.</span></span>|  
|<span data-ttu-id="20d91-113">Proprietà <xref:System.Media.SoundPlayer.LoadTimeout%2A></span><span class="sxs-lookup"><span data-stu-id="20d91-113"><xref:System.Media.SoundPlayer.LoadTimeout%2A> property</span></span>|<span data-ttu-id="20d91-114">Numero di millisecondi di attesa per caricare un suono prima genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="20d91-114">The number of milliseconds your program will wait to load a sound before it throws an exception.</span></span> <span data-ttu-id="20d91-115">Il valore predefinito è 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="20d91-115">The default is 10 seconds.</span></span>|  
|<span data-ttu-id="20d91-116">Proprietà <xref:System.Media.SoundPlayer.IsLoadCompleted%2A></span><span class="sxs-lookup"><span data-stu-id="20d91-116"><xref:System.Media.SoundPlayer.IsLoadCompleted%2A> property</span></span>|<span data-ttu-id="20d91-117">Valore booleano che indica se l'audio è stato caricato.</span><span class="sxs-lookup"><span data-stu-id="20d91-117">A Boolean value indicating whether the sound has finished loading.</span></span>|  
|<span data-ttu-id="20d91-118">Metodo <xref:System.Media.SoundPlayer.Load%2A></span><span class="sxs-lookup"><span data-stu-id="20d91-118"><xref:System.Media.SoundPlayer.Load%2A> method</span></span>|<span data-ttu-id="20d91-119">Carica un suono in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="20d91-119">Loads a sound synchronously.</span></span>|  
|<span data-ttu-id="20d91-120">Metodo <xref:System.Media.SoundPlayer.LoadAsync%2A></span><span class="sxs-lookup"><span data-stu-id="20d91-120"><xref:System.Media.SoundPlayer.LoadAsync%2A> method</span></span>|<span data-ttu-id="20d91-121">Inizia a caricare in modo asincrono un suono.</span><span class="sxs-lookup"><span data-stu-id="20d91-121">Begins to load a sound asynchronously.</span></span> <span data-ttu-id="20d91-122">Una volta completato il caricamento, viene generato il <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> evento.</span><span class="sxs-lookup"><span data-stu-id="20d91-122">When loading is complete, it raises the <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> event.</span></span>|  
|<span data-ttu-id="20d91-123">Metodo <xref:System.Media.SoundPlayer.Play%2A></span><span class="sxs-lookup"><span data-stu-id="20d91-123"><xref:System.Media.SoundPlayer.Play%2A> method</span></span>|<span data-ttu-id="20d91-124">Riproduce il suono specificato nella <xref:System.Media.SoundPlayer.SoundLocation%2A> o <xref:System.Media.SoundPlayer.Stream%2A> proprietà in un nuovo thread.</span><span class="sxs-lookup"><span data-stu-id="20d91-124">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in a new thread.</span></span>|  
|<span data-ttu-id="20d91-125">Metodo <xref:System.Media.SoundPlayer.PlaySync%2A></span><span class="sxs-lookup"><span data-stu-id="20d91-125"><xref:System.Media.SoundPlayer.PlaySync%2A> method</span></span>|<span data-ttu-id="20d91-126">Riproduce il suono specificato nella <xref:System.Media.SoundPlayer.SoundLocation%2A> o <xref:System.Media.SoundPlayer.Stream%2A> proprietà nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="20d91-126">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in the current thread.</span></span>|  
|<span data-ttu-id="20d91-127">Metodo <xref:System.Media.SoundPlayer.Stop%2A></span><span class="sxs-lookup"><span data-stu-id="20d91-127"><xref:System.Media.SoundPlayer.Stop%2A> method</span></span>|<span data-ttu-id="20d91-128">Arresta un suono.</span><span class="sxs-lookup"><span data-stu-id="20d91-128">Stops any sound currently playing.</span></span>|  
|<span data-ttu-id="20d91-129">Evento<xref:System.Media.SoundPlayer.LoadCompleted> </span><span class="sxs-lookup"><span data-stu-id="20d91-129"><xref:System.Media.SoundPlayer.LoadCompleted> event</span></span>|<span data-ttu-id="20d91-130">Generato dopo il tentativo di caricamento di un suono.</span><span class="sxs-lookup"><span data-stu-id="20d91-130">Raised after the load of a sound is attempted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="20d91-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20d91-131">See also</span></span>

- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>
