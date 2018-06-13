---
title: Cenni preliminari sul controllo StatusStrip
ms.date: 03/30/2017
f1_keywords:
- StatusStrip
helpviewer_keywords:
- StatusStrip control [Windows Forms], about StatusStrip control
- status bars [Windows Forms], about status bars
ms.assetid: c0d9bcbb-f8b8-46ef-bae2-4146b8c8ce99
ms.openlocfilehash: b915be2db6865a95d2d37afda58983dbb2edca27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537908"
---
# <a name="statusstrip-control-overview"></a><span data-ttu-id="facd6-102">Cenni preliminari sul controllo StatusStrip</span><span class="sxs-lookup"><span data-stu-id="facd6-102">StatusStrip Control Overview</span></span>
<span data-ttu-id="facd6-103">In un controllo <xref:System.Windows.Forms.StatusStrip> sono in genere presenti informazioni su un oggetto visualizzato su un <xref:System.Windows.Forms.Form>, sui componenti dell'oggetto o informazioni contestuali collegate alle operazioni di tale oggetto all'interno dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="facd6-103">A <xref:System.Windows.Forms.StatusStrip> control displays information about an object being viewed on a <xref:System.Windows.Forms.Form>, the object's components, or contextual information that relates to that object's operation within your application.</span></span> <span data-ttu-id="facd6-104">In genere, un controllo <xref:System.Windows.Forms.StatusStrip> è composto da oggetti <xref:System.Windows.Forms.ToolStripStatusLabel>, in ciascuno dei quali è visualizzato un testo e/o un'icona.</span><span class="sxs-lookup"><span data-stu-id="facd6-104">Typically, a <xref:System.Windows.Forms.StatusStrip> control consists of <xref:System.Windows.Forms.ToolStripStatusLabel> objects, each of which displays text, an icon, or both.</span></span> <span data-ttu-id="facd6-105">Il controllo <xref:System.Windows.Forms.StatusStrip> può contenere anche controlli <xref:System.Windows.Forms.ToolStripDropDownButton>, <xref:System.Windows.Forms.ToolStripSplitButton> e <xref:System.Windows.Forms.ToolStripProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="facd6-105">The <xref:System.Windows.Forms.StatusStrip> can also contain <xref:System.Windows.Forms.ToolStripDropDownButton>, <xref:System.Windows.Forms.ToolStripSplitButton>, and <xref:System.Windows.Forms.ToolStripProgressBar> controls.</span></span>  
  
 <span data-ttu-id="facd6-106">Il valore predefinito <xref:System.Windows.Forms.StatusStrip> non ha pannelli.</span><span class="sxs-lookup"><span data-stu-id="facd6-106">The default <xref:System.Windows.Forms.StatusStrip> has no panels.</span></span> <span data-ttu-id="facd6-107">Per aggiungere pannelli a un controllo <xref:System.Windows.Forms.StatusStrip> usare il metodo <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="facd6-107">To add panels to a <xref:System.Windows.Forms.StatusStrip>, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="facd6-108">Esiste supporto completo per la gestione di elementi e comandi comuni di <xref:System.Windows.Forms.StatusStrip> in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="facd6-108">There is extensive support for handling <xref:System.Windows.Forms.StatusStrip> items and common commands in Visual Studio.</span></span>  
  
 <span data-ttu-id="facd6-109">Vedere anche [Editor raccolta Items di StatusStrip](http://msdn.microsoft.com/library/ms233631\(v=vs.110\)), [la finestra di dialogo attività di StatusStrip](http://msdn.microsoft.com/library/ms233642\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="facd6-109">Also see [StatusStrip Items Collection Editor](http://msdn.microsoft.com/library/ms233631\(v=vs.110\)), [StatusStrip Tasks Dialog Box](http://msdn.microsoft.com/library/ms233642\(v=vs.110\)).</span></span>  
  
 <span data-ttu-id="facd6-110">Benché il controllo <xref:System.Windows.Forms.StatusStrip> sostituisca ed estenda il controllo <xref:System.Windows.Forms.StatusBar> delle versioni precedenti, il controllo <xref:System.Windows.Forms.StatusBar> viene mantenuto per compatibilità con le versioni precedenti e per eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="facd6-110">Although <xref:System.Windows.Forms.StatusStrip> replaces and extends the <xref:System.Windows.Forms.StatusBar> control of previous versions, <xref:System.Windows.Forms.StatusBar> is retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="important-statusstrip-members"></a><span data-ttu-id="facd6-111">Membri importanti di StatusStrip</span><span class="sxs-lookup"><span data-stu-id="facd6-111">Important StatusStrip Members</span></span>  
  
|<span data-ttu-id="facd6-112">Nome</span><span class="sxs-lookup"><span data-stu-id="facd6-112">Name</span></span>|<span data-ttu-id="facd6-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="facd6-113">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.StatusStrip.CanOverflow%2A>|<span data-ttu-id="facd6-114">Ottiene o imposta un valore che indica se il controllo <xref:System.Windows.Forms.StatusStrip> supporta la funzionalità di overflow.</span><span class="sxs-lookup"><span data-stu-id="facd6-114">Gets or sets a value indicating whether the <xref:System.Windows.Forms.StatusStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.StatusStrip.Stretch%2A>|<span data-ttu-id="facd6-115">Ottiene o imposta un valore che indica se il controllo <xref:System.Windows.Forms.StatusStrip> si estende da un'estremità all'altra nella propria classe <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="facd6-115">Gets or sets a value indicating whether the <xref:System.Windows.Forms.StatusStrip> stretches from end to end in its <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
  
### <a name="important-statusstrip-companion-classes"></a><span data-ttu-id="facd6-116">Classi importanti correlate a StatusStrip</span><span class="sxs-lookup"><span data-stu-id="facd6-116">Important StatusStrip Companion Classes</span></span>  
  
|<span data-ttu-id="facd6-117">Nome</span><span class="sxs-lookup"><span data-stu-id="facd6-117">Name</span></span>|<span data-ttu-id="facd6-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="facd6-118">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripStatusLabel>|<span data-ttu-id="facd6-119">Rappresenta un pannello in un controllo <xref:System.Windows.Forms.StatusStrip>.</span><span class="sxs-lookup"><span data-stu-id="facd6-119">Represents a panel in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownButton>|<span data-ttu-id="facd6-120">Visualizza un oggetto <xref:System.Windows.Forms.ToolStripDropDown> associato dal quale l'utente può selezionare un singolo elemento.</span><span class="sxs-lookup"><span data-stu-id="facd6-120">Displays an associated <xref:System.Windows.Forms.ToolStripDropDown> from which the user can select a single item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripSplitButton>|<span data-ttu-id="facd6-121">Rappresenta un controllo in due parti con un pulsante standard e un menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="facd6-121">Represents a two-part control that is a standard button and a drop-down menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar>|<span data-ttu-id="facd6-122">Visualizza lo stato di completamento di un processo.</span><span class="sxs-lookup"><span data-stu-id="facd6-122">Displays the completion state of a process.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="facd6-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="facd6-123">See Also</span></span>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>
