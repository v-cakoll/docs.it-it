---
ms.openlocfilehash: 9659068304eb208fd6a0a753273453bc669fbc56
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621271"
---
### <a name="keytips-behavior-improved-in-wpf"></a><span data-ttu-id="6975c-101">Miglioramento del comportamento dei suggerimenti tasto di scelta in WPF</span><span class="sxs-lookup"><span data-stu-id="6975c-101">Keytips behavior improved in WPF</span></span>

#### <a name="details"></a><span data-ttu-id="6975c-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6975c-102">Details</span></span>

<span data-ttu-id="6975c-103">Il comportamento dei suggerimenti tasto di scelta è stato modificato in modo che fosse alla pari con il comportamento in Microsoft Word e in Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="6975c-103">Keytips behavior has been modified to bring parity with behavior on Microsoft Word and Windows Explorer.</span></span> <span data-ttu-id="6975c-104">Controllando se lo stato dei suggerimenti tasto di scelta corrisponde o meno ad Abilitato in caso di pressione di un <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particolare <xref:System.Windows.Input.Key> o <xref:System.Windows.Input.Key.F11>), WPF gestisce i tasti dei suggerimenti tasto di scelta in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="6975c-104">By checking whether keytip state is enabled or not in the case of a <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particular, <xref:System.Windows.Input.Key> or <xref:System.Windows.Input.Key.F11>) being pressed, WPF handles keytip keys appropriately.</span></span> <span data-ttu-id="6975c-105">I suggerimenti tasto di scelta ora chiudono un menu anche se è stato aperto tramite mouse.</span><span class="sxs-lookup"><span data-stu-id="6975c-105">Keytips now dismiss a menu even when it is opened by mouse.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6975c-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="6975c-106">Suggestion</span></span>

<span data-ttu-id="6975c-107">N/D</span><span class="sxs-lookup"><span data-stu-id="6975c-107">N/A</span></span>

| <span data-ttu-id="6975c-108">Nome</span><span class="sxs-lookup"><span data-stu-id="6975c-108">Name</span></span>    | <span data-ttu-id="6975c-109">Valore</span><span class="sxs-lookup"><span data-stu-id="6975c-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6975c-110">Scope</span><span class="sxs-lookup"><span data-stu-id="6975c-110">Scope</span></span>   |<span data-ttu-id="6975c-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6975c-111">Edge</span></span>|
|<span data-ttu-id="6975c-112">Version</span><span class="sxs-lookup"><span data-stu-id="6975c-112">Version</span></span>|<span data-ttu-id="6975c-113">4.7.2</span><span class="sxs-lookup"><span data-stu-id="6975c-113">4.7.2</span></span>|
|<span data-ttu-id="6975c-114">Type</span><span class="sxs-lookup"><span data-stu-id="6975c-114">Type</span></span>|<span data-ttu-id="6975c-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="6975c-115">Runtime</span></span>|
