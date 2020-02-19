---
ms.openlocfilehash: dc733ee32184db5af59bb06e294cd73765977581
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449557"
---
### <a name="fieldinfosetvalue-throws-exception-for-static-init-only-fields"></a><span data-ttu-id="2d4cb-101">FieldInfo. SetValue genera un'eccezione per i campi statici di sola inizializzazione</span><span class="sxs-lookup"><span data-stu-id="2d4cb-101">FieldInfo.SetValue throws exception for static, init-only fields</span></span>

<span data-ttu-id="2d4cb-102">A partire da .NET Core 3,0, viene generata un'eccezione quando si tenta di impostare un valore in un campo statico <xref:System.Reflection.FieldAttributes.InitOnly> chiamando <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="2d4cb-102">Starting in .NET Core 3.0, an exception is thrown when you attempt to set a value on a static, <xref:System.Reflection.FieldAttributes.InitOnly> field by calling <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="2d4cb-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="2d4cb-103">Change description</span></span>

<span data-ttu-id="2d4cb-104">In .NET Framework e versioni di .NET Core precedenti alla 3,0, è possibile impostare il valore di un campo statico che è costante dopo l'inizializzazione ([ReadOnly in C# ](~/docs/csharp/language-reference/keywords/readonly.md)) chiamando <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="2d4cb-104">In .NET Framework and versions of .NET Core prior to 3.0, you could set the value of a static field that's constant after it is initialized ([readonly in C#](~/docs/csharp/language-reference/keywords/readonly.md)) by calling <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="2d4cb-105">Tuttavia, l'impostazione di tale campo in questo modo comporta un comportamento imprevedibile basato sul Framework di destinazione e sulle impostazioni di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="2d4cb-105">However, setting such a field in this way resulted in unpredictable behavior based on the target framework and optimization settings.</span></span>

<span data-ttu-id="2d4cb-106">In .NET Core 3,0 e versioni successive, quando si chiama <xref:System.Reflection.FieldInfo.SetValue%2A> su un campo statico <xref:System.Reflection.FieldAttributes.InitOnly>, viene generata un'eccezione <xref:System.FieldAccessException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2d4cb-106">In .NET Core 3.0 and later versions, when you call <xref:System.Reflection.FieldInfo.SetValue%2A> on a static, <xref:System.Reflection.FieldAttributes.InitOnly> field, a <xref:System.FieldAccessException?displayProperty=nameWithType> exception is thrown.</span></span>

> [!TIP]
> <span data-ttu-id="2d4cb-107">Un campo <xref:System.Reflection.FieldAttributes.InitOnly> è un campo che può essere impostato solo nel momento in cui è dichiarato o nel costruttore per la classe che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="2d4cb-107">An <xref:System.Reflection.FieldAttributes.InitOnly> field is one that can only be set at the time it's declared or in the constructor for the containing class.</span></span> <span data-ttu-id="2d4cb-108">In altre parole, è costante dopo l'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="2d4cb-108">In other words, it's constant after it is initialized.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2d4cb-109">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="2d4cb-109">Version introduced</span></span>

<span data-ttu-id="2d4cb-110">3.0</span><span class="sxs-lookup"><span data-stu-id="2d4cb-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2d4cb-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="2d4cb-111">Recommended action</span></span>

<span data-ttu-id="2d4cb-112">Inizializzare i campi statici <xref:System.Reflection.FieldAttributes.InitOnly> in un costruttore statico.</span><span class="sxs-lookup"><span data-stu-id="2d4cb-112">Initialize static, <xref:System.Reflection.FieldAttributes.InitOnly> fields in a static constructor.</span></span> <span data-ttu-id="2d4cb-113">Questo vale per i tipi dinamici e non dinamici.</span><span class="sxs-lookup"><span data-stu-id="2d4cb-113">This applies to both dynamic and non-dynamic types.</span></span>

<span data-ttu-id="2d4cb-114">In alternativa, è possibile rimuovere l'attributo <xref:System.Reflection.FieldAttributes.InitOnly?displayProperty=nameWithType> dal campo, quindi chiamare <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2d4cb-114">Alternatively, you can remove the <xref:System.Reflection.FieldAttributes.InitOnly?displayProperty=nameWithType> attribute from the field, and then call <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="2d4cb-115">Category</span><span class="sxs-lookup"><span data-stu-id="2d4cb-115">Category</span></span>

<span data-ttu-id="2d4cb-116">CoreFx</span><span class="sxs-lookup"><span data-stu-id="2d4cb-116">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2d4cb-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="2d4cb-117">Affected APIs</span></span>

- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)?displayProperty=nameWithType>
- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)`
- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)`

-->
