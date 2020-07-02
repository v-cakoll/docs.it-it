---
ms.openlocfilehash: 598df2121b480d411dac9c5571772a4a8d22b5ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620341"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a><span data-ttu-id="f7f2d-101">I cataloghi MEF implementano IEnumerable e quindi non è più possibile usarli per creare un serializzatore</span><span class="sxs-lookup"><span data-stu-id="f7f2d-101">MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer</span></span>

#### <a name="details"></a><span data-ttu-id="f7f2d-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f7f2d-102">Details</span></span>

<span data-ttu-id="f7f2d-103">A partire da .NET Framework 4.5, i cataloghi MEF implementano IEnumerable e quindi non è più possibile usarli per creare un serializzatore (oggetto <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="f7f2d-103">Starting with the .NET Framework 4.5, MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> object).</span></span> <span data-ttu-id="f7f2d-104">Il tentativo di serializzare un catalogo MEF genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="f7f2d-104">Trying to serialize a MEF catalog throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f7f2d-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="f7f2d-105">Suggestion</span></span>

<span data-ttu-id="f7f2d-106">Non è più possibile usare MEF per creare un serializzatore</span><span class="sxs-lookup"><span data-stu-id="f7f2d-106">Can no longer use MEF to create a serializer</span></span>

| <span data-ttu-id="f7f2d-107">Nome</span><span class="sxs-lookup"><span data-stu-id="f7f2d-107">Name</span></span>    | <span data-ttu-id="f7f2d-108">Valore</span><span class="sxs-lookup"><span data-stu-id="f7f2d-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f7f2d-109">Scope</span><span class="sxs-lookup"><span data-stu-id="f7f2d-109">Scope</span></span>   |<span data-ttu-id="f7f2d-110">Principale</span><span class="sxs-lookup"><span data-stu-id="f7f2d-110">Major</span></span>|
|<span data-ttu-id="f7f2d-111">Version</span><span class="sxs-lookup"><span data-stu-id="f7f2d-111">Version</span></span>|<span data-ttu-id="f7f2d-112">4.5</span><span class="sxs-lookup"><span data-stu-id="f7f2d-112">4.5</span></span>|
|<span data-ttu-id="f7f2d-113">Type</span><span class="sxs-lookup"><span data-stu-id="f7f2d-113">Type</span></span>|<span data-ttu-id="f7f2d-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="f7f2d-114">Runtime</span></span>|
