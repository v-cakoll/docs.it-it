---
ms.openlocfilehash: a54b17b2002bd0f85b8b47c5e37e040470d6c494
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621331"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a><span data-ttu-id="66096-101">Gli oggetti Reflection non possono essere più passati dal codice gestito ai client DCOM out-of-process</span><span class="sxs-lookup"><span data-stu-id="66096-101">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients</span></span>

#### <a name="details"></a><span data-ttu-id="66096-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="66096-102">Details</span></span>

<span data-ttu-id="66096-103">Gli oggetti di reflection non possono essere più passati dal codice gestito ai client DCOM out-of-process.</span><span class="sxs-lookup"><span data-stu-id="66096-103">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients.</span></span> <span data-ttu-id="66096-104">Sono interessati i tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="66096-104">The following types are affected:</span></span><ul><li><xref:System.Reflection.Assembly?displayProperty=fullName></li><li><span data-ttu-id="66096-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> e i tipi derivati, inclusi <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName> e <xref:System.Reflection.TypeInfo?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="66096-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (and its derived types, including <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName>, and <xref:System.Reflection.TypeInfo?displayProperty=fullName>)</span></span></li><li><xref:System.Reflection.MethodBody?displayProperty=fullName></li><li><xref:System.Reflection.Module?displayProperty=fullName></li><li><span data-ttu-id="66096-106"><xref:System.Reflection.ParameterInfo?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="66096-106"><xref:System.Reflection.ParameterInfo?displayProperty=fullName>.</span></span></li></ul><span data-ttu-id="66096-107">Le chiamate a <code>IMarshal</code> per l'oggetto restituiscono <code>E_NOINTERFACE</code>.</span><span class="sxs-lookup"><span data-stu-id="66096-107">Calls to <code>IMarshal</code> for the object return <code>E_NOINTERFACE</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="66096-108">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="66096-108">Suggestion</span></span>

<span data-ttu-id="66096-109">Aggiornare il codice di marshalling in modo che funzioni con oggetti non di reflection</span><span class="sxs-lookup"><span data-stu-id="66096-109">Update marshaling code to work with non-reflection objects</span></span>

| <span data-ttu-id="66096-110">Nome</span><span class="sxs-lookup"><span data-stu-id="66096-110">Name</span></span>    | <span data-ttu-id="66096-111">Valore</span><span class="sxs-lookup"><span data-stu-id="66096-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="66096-112">Scope</span><span class="sxs-lookup"><span data-stu-id="66096-112">Scope</span></span>   |<span data-ttu-id="66096-113">Minorenne</span><span class="sxs-lookup"><span data-stu-id="66096-113">Minor</span></span>|
|<span data-ttu-id="66096-114">Version</span><span class="sxs-lookup"><span data-stu-id="66096-114">Version</span></span>|<span data-ttu-id="66096-115">4.6</span><span class="sxs-lookup"><span data-stu-id="66096-115">4.6</span></span>|
|<span data-ttu-id="66096-116">Type</span><span class="sxs-lookup"><span data-stu-id="66096-116">Type</span></span>|<span data-ttu-id="66096-117">Runtime</span><span class="sxs-lookup"><span data-stu-id="66096-117">Runtime</span></span>|
