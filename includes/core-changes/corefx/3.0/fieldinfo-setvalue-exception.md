---
ms.openlocfilehash: dc733ee32184db5af59bb06e294cd73765977581
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449557"
---
### <a name="fieldinfosetvalue-throws-exception-for-static-init-only-fields"></a><span data-ttu-id="72859-101">FieldInfo.SetValue genera un'eccezione per i campi statici di solo init</span><span class="sxs-lookup"><span data-stu-id="72859-101">FieldInfo.SetValue throws exception for static, init-only fields</span></span>

<span data-ttu-id="72859-102">A partire da .NET Core 3.0, viene generata un'eccezione quando si tenta di impostare un valore in un <xref:System.Reflection.FieldAttributes.InitOnly> campo statico chiamando <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="72859-102">Starting in .NET Core 3.0, an exception is thrown when you attempt to set a value on a static, <xref:System.Reflection.FieldAttributes.InitOnly> field by calling <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="72859-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="72859-103">Change description</span></span>

<span data-ttu-id="72859-104">In .NET Framework e nelle versioni di .NET Core precedenti alla 3.0, è possibile impostare il valore di un <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>campo statico costante dopo l'inizializzazione ([readonly in Cè](~/docs/csharp/language-reference/keywords/readonly.md)) chiamando .</span><span class="sxs-lookup"><span data-stu-id="72859-104">In .NET Framework and versions of .NET Core prior to 3.0, you could set the value of a static field that's constant after it is initialized ([readonly in C#](~/docs/csharp/language-reference/keywords/readonly.md)) by calling <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="72859-105">Tuttavia, l'impostazione di un campo di questo tipo in questo modo ha comportato un comportamento imprevedibile in base al framework di destinazione e alle impostazioni di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="72859-105">However, setting such a field in this way resulted in unpredictable behavior based on the target framework and optimization settings.</span></span>

<span data-ttu-id="72859-106">In .NET Core 3.0 e versioni <xref:System.Reflection.FieldInfo.SetValue%2A> successive, <xref:System.Reflection.FieldAttributes.InitOnly> quando si <xref:System.FieldAccessException?displayProperty=nameWithType> chiama su un campo statico, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="72859-106">In .NET Core 3.0 and later versions, when you call <xref:System.Reflection.FieldInfo.SetValue%2A> on a static, <xref:System.Reflection.FieldAttributes.InitOnly> field, a <xref:System.FieldAccessException?displayProperty=nameWithType> exception is thrown.</span></span>

> [!TIP]
> <span data-ttu-id="72859-107">Un <xref:System.Reflection.FieldAttributes.InitOnly> campo è un campo che può essere impostato solo al momento della visualizzazione o nel costruttore per la classe contenitore.</span><span class="sxs-lookup"><span data-stu-id="72859-107">An <xref:System.Reflection.FieldAttributes.InitOnly> field is one that can only be set at the time it's declared or in the constructor for the containing class.</span></span> <span data-ttu-id="72859-108">In altre parole, è costante dopo che è stato inizializzato.</span><span class="sxs-lookup"><span data-stu-id="72859-108">In other words, it's constant after it is initialized.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="72859-109">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="72859-109">Version introduced</span></span>

<span data-ttu-id="72859-110">3.0</span><span class="sxs-lookup"><span data-stu-id="72859-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="72859-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="72859-111">Recommended action</span></span>

<span data-ttu-id="72859-112">Inizializzare <xref:System.Reflection.FieldAttributes.InitOnly> i campi statici in un costruttore statico.</span><span class="sxs-lookup"><span data-stu-id="72859-112">Initialize static, <xref:System.Reflection.FieldAttributes.InitOnly> fields in a static constructor.</span></span> <span data-ttu-id="72859-113">Questo vale sia per i tipi dinamici che per i tipi non dinamici.</span><span class="sxs-lookup"><span data-stu-id="72859-113">This applies to both dynamic and non-dynamic types.</span></span>

<span data-ttu-id="72859-114">In alternativa, è <xref:System.Reflection.FieldAttributes.InitOnly?displayProperty=nameWithType> possibile rimuovere l'attributo <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=nameWithType>dal campo e quindi chiamare .</span><span class="sxs-lookup"><span data-stu-id="72859-114">Alternatively, you can remove the <xref:System.Reflection.FieldAttributes.InitOnly?displayProperty=nameWithType> attribute from the field, and then call <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="72859-115">Category</span><span class="sxs-lookup"><span data-stu-id="72859-115">Category</span></span>

<span data-ttu-id="72859-116">CoreFx</span><span class="sxs-lookup"><span data-stu-id="72859-116">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="72859-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="72859-117">Affected APIs</span></span>

- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)?displayProperty=nameWithType>
- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)`
- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)`

-->