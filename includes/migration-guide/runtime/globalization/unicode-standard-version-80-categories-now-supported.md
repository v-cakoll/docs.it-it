---
ms.openlocfilehash: 480cbdecd681408a7e1d6fa366e3f1a4b131ab42
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857588"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a><span data-ttu-id="7307a-101">Le categorie dello standard Unicode versione 8.0 sono ora supportate</span><span class="sxs-lookup"><span data-stu-id="7307a-101">Unicode standard version 8.0 categories now supported</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7307a-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7307a-102">Details</span></span>|<span data-ttu-id="7307a-103">In .NET Framework 4.6.2 i dati Unicode sono stati aggiornati dallo standard Unicode versione 6.3 alla versione 8.0.</span><span class="sxs-lookup"><span data-stu-id="7307a-103">In .NET Framework 4.6.2, Unicode data has been upgraded from Unicode Standard version 6.3 to version 8.0.</span></span>  <span data-ttu-id="7307a-104">Quando si richiedono le categorie di caratteri Unicode in .NET Framework 4.6.2, alcuni risultati potrebbero non corrispondere ai risultati ottenuti nelle versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7307a-104">When requesting Unicode character categories in .NET Framework 4.6.2, some results might not match the results in previous .NET Framework versions.</span></span>  <span data-ttu-id="7307a-105">Questa modifica interessa principalmente le sillabe Cherokee e i simboli delle vocali e dei toni di Tai Lue semplificato.</span><span class="sxs-lookup"><span data-stu-id="7307a-105">This change mostly affects Cherokee syllables and New Tai Lue vowels signs and tone marks.</span></span>|
|<span data-ttu-id="7307a-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="7307a-106">Suggestion</span></span>|<span data-ttu-id="7307a-107">Esaminare il codice e rimuovere o modificare la logica che dipende dalle categorie di caratteri Unicode hardcoded.</span><span class="sxs-lookup"><span data-stu-id="7307a-107">Review code and remove/change logic that depends on hard-coded Unicode character categories.</span></span>|
|<span data-ttu-id="7307a-108">Ambito</span><span class="sxs-lookup"><span data-stu-id="7307a-108">Scope</span></span>|<span data-ttu-id="7307a-109">Secondario</span><span class="sxs-lookup"><span data-stu-id="7307a-109">Minor</span></span>|
|<span data-ttu-id="7307a-110">Versione</span><span class="sxs-lookup"><span data-stu-id="7307a-110">Version</span></span>|<span data-ttu-id="7307a-111">4.6.2</span><span class="sxs-lookup"><span data-stu-id="7307a-111">4.6.2</span></span>|
|<span data-ttu-id="7307a-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="7307a-112">Type</span></span>|<span data-ttu-id="7307a-113">Runtime</span><span class="sxs-lookup"><span data-stu-id="7307a-113">Runtime</span></span>|
|<span data-ttu-id="7307a-114">API interessate</span><span class="sxs-lookup"><span data-stu-id="7307a-114">Affected APIs</span></span>|<ul><li><xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|

