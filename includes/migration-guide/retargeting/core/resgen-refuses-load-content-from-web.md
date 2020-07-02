---
ms.openlocfilehash: f980c8029375074889505a8eb7e8a65aaa8d74e4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614520"
---
### <a name="resgen-refuses-to-load-content-from-the-web"></a><span data-ttu-id="b2076-101">Resgen rifiuta di caricare il contenuto dal Web</span><span class="sxs-lookup"><span data-stu-id="b2076-101">Resgen refuses to load content from the web</span></span>

#### <a name="details"></a><span data-ttu-id="b2076-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b2076-102">Details</span></span>

<span data-ttu-id="b2076-103">i file con estensione resx possono contenere input in formato binario.</span><span class="sxs-lookup"><span data-stu-id="b2076-103">.resx files may contain binary formatted input.</span></span> <span data-ttu-id="b2076-104">Se si tenta di utilizzare Resgen per caricare un file scaricato da un percorso non attendibile, non sarà possibile caricare l'input per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b2076-104">If you attempt to use resgen to load a file that was downloaded from an untrusted location, it will fail to load the input by default.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b2076-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="b2076-105">Suggestion</span></span>

<span data-ttu-id="b2076-106">Gli utenti di Resgen che richiedono il caricamento di input in formato binario da percorsi non attendibili possono rimuovere il contrassegno del Web dal file di input o applicare lo stravaganza esplicita. Aggiungere l'impostazione del registro di sistema seguente per applicare il rifiuto esplicito a livello di computer: [HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft.netframework\sdk] &quot; AllowProcessOfUntrustedResourceFiles &quot; = &quot; true&quot;</span><span class="sxs-lookup"><span data-stu-id="b2076-106">Resgen users who require loading binary formatted input from untrusted locations can either remove the mark of the web from the input file or apply the opt-out quirk.Add the following registry setting to apply the machine wide opt-out quirk: [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework\SDK] &quot;AllowProcessOfUntrustedResourceFiles&quot;=&quot;true&quot;</span></span>

| <span data-ttu-id="b2076-107">Nome</span><span class="sxs-lookup"><span data-stu-id="b2076-107">Name</span></span>    | <span data-ttu-id="b2076-108">Valore</span><span class="sxs-lookup"><span data-stu-id="b2076-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b2076-109">Scope</span><span class="sxs-lookup"><span data-stu-id="b2076-109">Scope</span></span>   | <span data-ttu-id="b2076-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b2076-110">Edge</span></span>        |
| <span data-ttu-id="b2076-111">Version</span><span class="sxs-lookup"><span data-stu-id="b2076-111">Version</span></span> | <span data-ttu-id="b2076-112">4.7.2</span><span class="sxs-lookup"><span data-stu-id="b2076-112">4.7.2</span></span>       |
| <span data-ttu-id="b2076-113">Type</span><span class="sxs-lookup"><span data-stu-id="b2076-113">Type</span></span>    | <span data-ttu-id="b2076-114">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="b2076-114">Retargeting</span></span> |
