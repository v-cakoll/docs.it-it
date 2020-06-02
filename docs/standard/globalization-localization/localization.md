---
title: Localizzazione
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- culture, localization
- application development [.NET Framework], localization
- globalization [.NET Framework], localization
- code blocks
- international applications [.NET Framework], localization
- global applications, localization
- world-ready applications, localization
- user interface blocks
- localization [.NET Framework], about localization
- localizing resources
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
ms.openlocfilehash: 68e877088c5c3d17b368561b563b4cb17d004e75
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84278025"
---
# <a name="localization"></a><span data-ttu-id="c6207-102">Localizzazione</span><span class="sxs-lookup"><span data-stu-id="c6207-102">Localization</span></span>

<span data-ttu-id="c6207-103">La localizzazione è il processo di conversione delle risorse di un'applicazione nelle versioni localizzate per tutte le impostazioni cultura supportate dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c6207-103">Localization is the process of translating an application's resources into localized versions for each culture that the application will support.</span></span> <span data-ttu-id="c6207-104">È consigliabile passare alla fase di localizzazione solo dopo aver completato il passaggio di [revisione della localizzabilità](localizability-review.md), per verificare che l'applicazione globalizzata sia pronta per la localizzazione.</span><span class="sxs-lookup"><span data-stu-id="c6207-104">You should proceed to the localization step only after completing the [Localizability Review](localizability-review.md) step to verify that the globalized application is ready for localization.</span></span>

<span data-ttu-id="c6207-105">Un'applicazione pronta per la localizzazione è suddivisa in due blocchi concettuali: un blocco che contiene tutti gli elementi dell'interfaccia utente e un blocco che contiene il codice eseguibile.</span><span class="sxs-lookup"><span data-stu-id="c6207-105">An application that is ready for localization is separated into two conceptual blocks: a block that contains all user interface elements and a block that contains executable code.</span></span> <span data-ttu-id="c6207-106">Il blocco dell'interfaccia utente contiene solo gli elementi dell'interfaccia utente localizzabili, come stringhe, messaggi di errore, finestre di dialogo, menu, risorse oggetto incorporate e così via, per le impostazioni cultura neutre.</span><span class="sxs-lookup"><span data-stu-id="c6207-106">The user interface block contains only localizable user-interface elements such as strings, error messages, dialog boxes, menus, embedded object resources, and so on for the neutral culture.</span></span> <span data-ttu-id="c6207-107">Il blocco di codice contiene solo il codice dell'applicazione che deve essere usato da tutte le impostazioni cultura supportate.</span><span class="sxs-lookup"><span data-stu-id="c6207-107">The code block contains only the application code to be used by all supported cultures.</span></span> <span data-ttu-id="c6207-108">Common Language Runtime supporta un modello di risorse assembly satellite che separa il codice eseguibile dell'applicazione dalle relative risorse.</span><span class="sxs-lookup"><span data-stu-id="c6207-108">The common language runtime supports a satellite assembly resource model that separates an application's executable code from its resources.</span></span> <span data-ttu-id="c6207-109">Per altre informazioni sull'implementazione di questo modello, vedere [Risorse nelle app .NET](../../framework/resources/index.md).</span><span class="sxs-lookup"><span data-stu-id="c6207-109">For more information about implementing this model, see [Resources in .NET](../../framework/resources/index.md).</span></span>

<span data-ttu-id="c6207-110">Per ogni versione localizzata dell'applicazione, aggiungere un nuovo assembly satellite che contiene il blocco dell'interfaccia utente localizzata tradotto nella lingua appropriata per le impostazioni cultura di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c6207-110">For each localized version of your application, add a new satellite assembly that contains the localized user interface block translated into the appropriate language for the target culture.</span></span> <span data-ttu-id="c6207-111">Il blocco di codice per tutte le impostazioni cultura deve rimanere invariato.</span><span class="sxs-lookup"><span data-stu-id="c6207-111">The code block for all cultures should remain the same.</span></span> <span data-ttu-id="c6207-112">La combinazione di una versione localizzata del blocco dell'interfaccia utente con il blocco di codice produce una versione localizzata dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c6207-112">The combination of a localized version of the user interface block with the code block produces a localized version of your application.</span></span>

<span data-ttu-id="c6207-113">Windows Software Development Kit (SDK) fornisce l'editor di risorse di Windows Form (Winres.exe) che consente di localizzare rapidamente le risorse Windows Form per le impostazioni cultura di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c6207-113">The Windows Software Development Kit (SDK) supplies the Windows Forms Resource Editor (Winres.exe) that allows you to quickly localize Windows Forms for target cultures.</span></span> <span data-ttu-id="c6207-114">Per informazioni sull'uso di questo strumento, vedere [Winres.exe (editor di risorse di Windows Form)](../../framework/tools/winres-exe-windows-forms-resource-editor.md).</span><span class="sxs-lookup"><span data-stu-id="c6207-114">For information about using this tool, see [Winres.exe (Windows Forms Resource Editor)](../../framework/tools/winres-exe-windows-forms-resource-editor.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c6207-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6207-115">See also</span></span>

- [<span data-ttu-id="c6207-116">Globalizzazione e localizzazione</span><span class="sxs-lookup"><span data-stu-id="c6207-116">Globalization and Localization</span></span>](index.md)
- [<span data-ttu-id="c6207-117">Revisione della localizzabilità</span><span class="sxs-lookup"><span data-stu-id="c6207-117">Localizability Review</span></span>](localizability-review.md)
- [<span data-ttu-id="c6207-118">Globalizzazione</span><span class="sxs-lookup"><span data-stu-id="c6207-118">Globalization</span></span>](globalization.md)
- [<span data-ttu-id="c6207-119">Risorse nelle applicazioni desktop</span><span class="sxs-lookup"><span data-stu-id="c6207-119">Resources in Desktop Apps</span></span>](../../framework/resources/index.md)
