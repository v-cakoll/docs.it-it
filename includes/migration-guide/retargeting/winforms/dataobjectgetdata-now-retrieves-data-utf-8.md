---
ms.openlocfilehash: 3f330d5e601d599231ef0336b785e677fe1d114e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616078"
---
### <a name="dataobjectgetdata-now-retrieves-data-as-utf-8"></a><span data-ttu-id="6bed5-101">DataObject.GetData ora recupera i dati come UTF-8</span><span class="sxs-lookup"><span data-stu-id="6bed5-101">DataObject.GetData now retrieves data as UTF-8</span></span>

#### <a name="details"></a><span data-ttu-id="6bed5-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6bed5-102">Details</span></span>

<span data-ttu-id="6bed5-103">Per le app destinate a .NET Framework 4 o che vengono eseguite in .NET Framework 4.5.1 o in versioni precedenti, `DataObject.GetData` recupera dati in formato HTML sotto forma di stringa ASCII.</span><span class="sxs-lookup"><span data-stu-id="6bed5-103">For apps that target the .NET Framework 4 or that run on the .NET Framework 4.5.1 or earlier versions, `DataObject.GetData` retrieves HTML-formatted data as an ASCII string.</span></span> <span data-ttu-id="6bed5-104">Di conseguenza, i caratteri non ASCII, ovvero quelli i cui codici ASCII sono maggiori di 0x7F, vengono rappresentati da due caratteri casuali.</span><span class="sxs-lookup"><span data-stu-id="6bed5-104">As a result, non-ASCII characters (characters whose ASCII codes are greater than 0x7F) are represented by two random characters.</span></span><p/><span data-ttu-id="6bed5-105">Per le app destinate a .NET Framework 4.5 o versione successiva ed eseguite in .NET Framework 4.5.2, `DataObject.GetData` recupera i dati in formato HTML come UTF-8, che rappresenta correttamente i caratteri con codici maggiori di 0x7F.</span><span class="sxs-lookup"><span data-stu-id="6bed5-105">For apps that target the .NET Framework 4.5 or later and run on the .NET Framework 4.5.2, `DataObject.GetData` retrieves HTML-formatted data as UTF-8, which represents characters greater than 0x7F correctly.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6bed5-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="6bed5-106">Suggestion</span></span>

<span data-ttu-id="6bed5-107">Se è stata implementata una soluzione alternativa per il problema di codifica con le stringhe in formato HTML, ad esempio codificando in modo esplicito la stringa HTML recuperata dagli Appunti passandola a <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>, e si intende ridestinare l'app dalla versione 4 alla versione 4.5, è necessario rimuovere questa soluzione alternativa. Se per qualche motivo è necessario il comportamento precedente, l'app può essere destinata a .NET Framework 4.0 per ottenere tale comportamento.</span><span class="sxs-lookup"><span data-stu-id="6bed5-107">If you implemented a workaround for the encoding problem with HTML-formatted strings (for example, by explicitly encoding the HTML string retrieved from the Clipboard by passing it to <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>) and you're retargeting your app from version 4 to 4.5, that workaround should be removed.If the old behavior is needed for some reason, the app can target the .NET Framework 4.0 to get that behavior.</span></span>

| <span data-ttu-id="6bed5-108">Nome</span><span class="sxs-lookup"><span data-stu-id="6bed5-108">Name</span></span>    | <span data-ttu-id="6bed5-109">Valore</span><span class="sxs-lookup"><span data-stu-id="6bed5-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6bed5-110">Scope</span><span class="sxs-lookup"><span data-stu-id="6bed5-110">Scope</span></span>   | <span data-ttu-id="6bed5-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6bed5-111">Edge</span></span>        |
| <span data-ttu-id="6bed5-112">Version</span><span class="sxs-lookup"><span data-stu-id="6bed5-112">Version</span></span> | <span data-ttu-id="6bed5-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="6bed5-113">4.5.2</span></span>       |
| <span data-ttu-id="6bed5-114">Type</span><span class="sxs-lookup"><span data-stu-id="6bed5-114">Type</span></span>    | <span data-ttu-id="6bed5-115">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="6bed5-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="6bed5-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="6bed5-116">Affected APIs</span></span>

- <xref:System.Windows.DataObject.GetData(System.String)?displayProperty=nameWithType>
- <xref:System.Windows.DataObject.GetData(System.Type)?displayProperty=nameWithType>
- <xref:System.Windows.DataObject.GetData(System.String,System.Boolean)?displayProperty=nameWithType>
