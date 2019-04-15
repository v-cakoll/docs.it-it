---
ms.openlocfilehash: a3f5f512fd17ab2b076f868be24e5c73d8698c49
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234207"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="32936-101">ObjectDisposedException generata dal controllo ortografico WPF</span><span class="sxs-lookup"><span data-stu-id="32936-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

|   |   |
|---|---|
|<span data-ttu-id="32936-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="32936-102">Details</span></span>|<span data-ttu-id="32936-103">Può verificarsi l'arresto anomalo di applicazioni WPF con un <xref:System.ObjectDisposedException?displayProperty=name> generato dal controllo ortografico.</span><span class="sxs-lookup"><span data-stu-id="32936-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=name> thrown by the spellchecker.</span></span> <span data-ttu-id="32936-104">Questo problema è risolto in .NET Framework 4.7 WPF, dove l'eccezione viene gestita in modo normale e pertanto si evitano effetti avversi sulle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="32936-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="32936-105">Si noti che potranno essere rilevate eccezioni first-chance occasionali nelle applicazioni in esecuzione in un debugger.</span><span class="sxs-lookup"><span data-stu-id="32936-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>|
|<span data-ttu-id="32936-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="32936-106">Suggestion</span></span>|<span data-ttu-id="32936-107">Effettuare l'aggiornamento a .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="32936-107">Upgrade to .NET Framework 4.7</span></span>|
|<span data-ttu-id="32936-108">Ambito</span><span class="sxs-lookup"><span data-stu-id="32936-108">Scope</span></span>|<span data-ttu-id="32936-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="32936-109">Edge</span></span>|
|<span data-ttu-id="32936-110">Versione</span><span class="sxs-lookup"><span data-stu-id="32936-110">Version</span></span>|<span data-ttu-id="32936-111">4.6.1</span><span class="sxs-lookup"><span data-stu-id="32936-111">4.6.1</span></span>|
|<span data-ttu-id="32936-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="32936-112">Type</span></span>|<span data-ttu-id="32936-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="32936-113">Runtime</span></span>|
