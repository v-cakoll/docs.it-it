---
ms.openlocfilehash: ed526095459a48aa37b585dfed79cc12b9fb9e56
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622044"
---
### <a name="some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a><span data-ttu-id="3a253-101">Alcune API .NET causano eccezioni EntryPointNotFoundException first-chance gestite</span><span class="sxs-lookup"><span data-stu-id="3a253-101">Some .NET APIs cause first chance (handled) EntryPointNotFoundExceptions</span></span>

#### <a name="details"></a><span data-ttu-id="3a253-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3a253-102">Details</span></span>

<span data-ttu-id="3a253-103">In .NET Framework 4.5, un numero limitato di metodi .NET ha iniziato a generare eccezioni <xref:System.EntryPointNotFoundException?displayProperty=fullName> first-chance.</span><span class="sxs-lookup"><span data-stu-id="3a253-103">In the .NET Framework 4.5, a small number of .NET methods began throwing first chance <xref:System.EntryPointNotFoundException?displayProperty=fullName>s.</span></span> <span data-ttu-id="3a253-104">Queste eccezioni erano gestite all'interno di .NET Framework, ma potevano interrompere l'automazione dei test che non prevedevano eccezioni first-chance.</span><span class="sxs-lookup"><span data-stu-id="3a253-104">These exceptions were handled within the .NET Framework, but could break test automation that did not expect the first chance exceptions.</span></span> <span data-ttu-id="3a253-105">Queste stesse API causano errori in alcuni scenari di ApiVerifier con HighVersionLie abilitato.</span><span class="sxs-lookup"><span data-stu-id="3a253-105">These same APIs break some ApiVerifier scenarios when HighVersionLie is enabled.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3a253-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="3a253-106">Suggestion</span></span>

<span data-ttu-id="3a253-107">È possibile evitare questo bug eseguendo l'aggiornamento a .NET Framework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="3a253-107">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="3a253-108">In alternativa, è possibile aggiornare l'automazione dei test in modo che non si interrompa in corrispondenza della prima <xref:System.EntryPointNotFoundException?displayProperty=fullName> first-chance.</span><span class="sxs-lookup"><span data-stu-id="3a253-108">Alternatively, test automation can be updated to not break on first-chance <xref:System.EntryPointNotFoundException?displayProperty=fullName>s.</span></span>

| <span data-ttu-id="3a253-109">Nome</span><span class="sxs-lookup"><span data-stu-id="3a253-109">Name</span></span>    | <span data-ttu-id="3a253-110">Valore</span><span class="sxs-lookup"><span data-stu-id="3a253-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3a253-111">Scope</span><span class="sxs-lookup"><span data-stu-id="3a253-111">Scope</span></span>   |<span data-ttu-id="3a253-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3a253-112">Edge</span></span>|
|<span data-ttu-id="3a253-113">Version</span><span class="sxs-lookup"><span data-stu-id="3a253-113">Version</span></span>|<span data-ttu-id="3a253-114">4.5</span><span class="sxs-lookup"><span data-stu-id="3a253-114">4.5</span></span>|
|<span data-ttu-id="3a253-115">Type</span><span class="sxs-lookup"><span data-stu-id="3a253-115">Type</span></span>|<span data-ttu-id="3a253-116">Runtime</span><span class="sxs-lookup"><span data-stu-id="3a253-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3a253-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="3a253-117">Affected APIs</span></span>

-<xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)></li></ul>|
