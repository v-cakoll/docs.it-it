---
ms.openlocfilehash: f87b70708398226516ab5eac32c24a9fc2c1106b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615736"
---
### <a name="xmlwriter-throws-on-invalid-surrogate-pairs"></a><span data-ttu-id="ed15e-101">XmlWriter genera un'eccezione per le coppie di surrogati non valide</span><span class="sxs-lookup"><span data-stu-id="ed15e-101">XmlWriter throws on invalid surrogate pairs</span></span>

#### <a name="details"></a><span data-ttu-id="ed15e-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ed15e-102">Details</span></span>

<span data-ttu-id="ed15e-103">Per le app destinate a .NET Framework 4.5.2 o a versioni precedenti, se si scrive una coppia di surrogati non valida usando la gestione dei fallback delle eccezioni, non viene sempre generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="ed15e-103">For apps that target the .NET Framework 4.5.2 or previous versions, writing an invalid surrogate pair using exception fallback handling does not always throw an exception.</span></span> <span data-ttu-id="ed15e-104">Per le applicazioni destinate a .NET Framework 4.6, il tentativo di scrivere una coppia di surrogati non valida genera <xref:System.ArgumentException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="ed15e-104">For apps that target the .NET Framework 4.6, attempting to write an invalid surrogate pair throws an <xref:System.ArgumentException?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ed15e-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="ed15e-105">Suggestion</span></span>

<span data-ttu-id="ed15e-106">Se necessario, questa interruzione può essere evitata specificando come destinazione .NET Framework 4.5.2 o versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="ed15e-106">If necessary, this break can be avoided by targeting the .NET Framework 4.5.2 or earlier.</span></span> <span data-ttu-id="ed15e-107">In alternativa, le coppie di surrogati non valide possono essere pre-elaborate in un xml valido prima di scriverle.</span><span class="sxs-lookup"><span data-stu-id="ed15e-107">Alternatively, invalid surrogate pairs can be pre-processed into valid xml prior to writing them.</span></span>

| <span data-ttu-id="ed15e-108">Nome</span><span class="sxs-lookup"><span data-stu-id="ed15e-108">Name</span></span>    | <span data-ttu-id="ed15e-109">Valore</span><span class="sxs-lookup"><span data-stu-id="ed15e-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ed15e-110">Scope</span><span class="sxs-lookup"><span data-stu-id="ed15e-110">Scope</span></span>   | <span data-ttu-id="ed15e-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ed15e-111">Edge</span></span>        |
| <span data-ttu-id="ed15e-112">Version</span><span class="sxs-lookup"><span data-stu-id="ed15e-112">Version</span></span> | <span data-ttu-id="ed15e-113">4.6</span><span class="sxs-lookup"><span data-stu-id="ed15e-113">4.6</span></span>         |
| <span data-ttu-id="ed15e-114">Type</span><span class="sxs-lookup"><span data-stu-id="ed15e-114">Type</span></span>    | <span data-ttu-id="ed15e-115">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="ed15e-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="ed15e-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="ed15e-116">Affected APIs</span></span>

- <xref:System.Xml.XmlWriter.WriteAttributeString(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteAttributeString(System.String,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteAttributeString(System.String,System.String,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteAttributeStringAsync(System.String,System.String,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteCData(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteCDataAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteChars(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteCharsAsync(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteComment(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteCommentAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteEntityRef(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteEntityRefAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteRaw(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteProcessingInstruction(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteProcessingInstructionAsync(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteRaw(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteRawAsync(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteRawAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteString(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteStringAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteSurrogateCharEntity(System.Char,System.Char)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteSurrogateCharEntityAsync(System.Char,System.Char)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteValue(System.String)?displayProperty=nameWithType>
