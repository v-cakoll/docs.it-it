---
ms.openlocfilehash: 5e2e8d1ec5d698d1c1649c2a0a1b4b77dbdf4022
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621280"
---
### <a name="wpf-printing-stack-update"></a><span data-ttu-id="b826f-101">Aggiornamento dello stack di stampa WPF</span><span class="sxs-lookup"><span data-stu-id="b826f-101">WPF Printing Stack Update</span></span>

#### <a name="details"></a><span data-ttu-id="b826f-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b826f-102">Details</span></span>

<span data-ttu-id="b826f-103">Le API di stampa di WPF che usano <xref:System.Printing.PrintQueue?displayProperty=fullName> ora chiamano l'API di gestione del pacchetto dei documenti di stampa di Windows invece dell'API di stampa XPS, ora deprecata.</span><span class="sxs-lookup"><span data-stu-id="b826f-103">WPF's Printing APIs using <xref:System.Printing.PrintQueue?displayProperty=fullName> now call Window's Print Document Package API in favor of the now deprecated XPS Print API.</span></span> <span data-ttu-id="b826f-104">La modifica è stata apportata per ottimizzare la funzionalità. Né gli utenti né gli sviluppatori dovrebbero riscontrare modifiche nel comportamento o nell'uso dell'API.</span><span class="sxs-lookup"><span data-stu-id="b826f-104">The change was made with serviceability in mind; neither users nor developers should see any changes in behavior or API usage.</span></span> <span data-ttu-id="b826f-105">Il nuovo stack di stampa viene abilitato per impostazione predefinita durante l'esecuzione in Windows 10 Creators Update.</span><span class="sxs-lookup"><span data-stu-id="b826f-105">The new printing stack is enabled by default when running in Windows 10 Creators Update.</span></span> <span data-ttu-id="b826f-106">Il vecchio stack di stampa continua a funzionare come in precedenza nelle versioni precedenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="b826f-106">The old printing stack will still continue to work just as before in older Windows versions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b826f-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="b826f-107">Suggestion</span></span>

<span data-ttu-id="b826f-108">Per usare lo stack precedente in Windows 10 Creators Update, impostare il valore <code>UseXpsOMPrinting</code> REG_DWORD della chiave del Registro di sistema <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> su <code>1</code>.</span><span class="sxs-lookup"><span data-stu-id="b826f-108">To use the old stack in Windows 10 Creators Update, set the <code>UseXpsOMPrinting</code> REG_DWORD value of the <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> registry key to <code>1</code>.</span></span>

| <span data-ttu-id="b826f-109">Nome</span><span class="sxs-lookup"><span data-stu-id="b826f-109">Name</span></span>    | <span data-ttu-id="b826f-110">Valore</span><span class="sxs-lookup"><span data-stu-id="b826f-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b826f-111">Scope</span><span class="sxs-lookup"><span data-stu-id="b826f-111">Scope</span></span>   |<span data-ttu-id="b826f-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b826f-112">Edge</span></span>|
|<span data-ttu-id="b826f-113">Version</span><span class="sxs-lookup"><span data-stu-id="b826f-113">Version</span></span>|<span data-ttu-id="b826f-114">4.7</span><span class="sxs-lookup"><span data-stu-id="b826f-114">4.7</span></span>|
|<span data-ttu-id="b826f-115">Type</span><span class="sxs-lookup"><span data-stu-id="b826f-115">Type</span></span>|<span data-ttu-id="b826f-116">Runtime</span><span class="sxs-lookup"><span data-stu-id="b826f-116">Runtime</span></span>|
