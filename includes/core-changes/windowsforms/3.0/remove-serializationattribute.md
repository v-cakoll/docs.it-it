---
ms.openlocfilehash: d48ced9d0201a33f9149aba155ddd3d8bc04c93f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74643956"
---
### <a name="serializableattribute-removed-from-some-windows-forms-types"></a><span data-ttu-id="c34d3-101">SerializableAttribute rimosso da alcuni tipi di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c34d3-101">SerializableAttribute removed from some Windows Forms types</span></span>

<span data-ttu-id="c34d3-102">L'oggetto <xref:System.SerializableAttribute> è stato rimosso da alcune classi Windows Form che non hanno scenari di serializzazione binaria noti.</span><span class="sxs-lookup"><span data-stu-id="c34d3-102">The <xref:System.SerializableAttribute> has been removed from some Windows Forms classes that have no known binary serialization scenarios.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c34d3-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="c34d3-103">Change description</span></span>

<span data-ttu-id="c34d3-104">I tipi seguenti sono <xref:System.SerializableAttribute> decorati con in .NET Framework, ma l'attributo è stato rimosso in .NET Core:</span><span class="sxs-lookup"><span data-stu-id="c34d3-104">The following types are decorated with the <xref:System.SerializableAttribute> in .NET Framework, but the attribute has been removed in .NET Core:</span></span>

- `System.InvariantComparer`
- <xref:System.ComponentModel.Design.ExceptionCollection?displayProperty=nameWithType>
- <xref:System.ComponentModel.Design.Serialization.CodeDomSerializerException?displayProperty=nameWithType>
- `System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService.CodeDomSerializationStore`
- <xref:System.Drawing.Design.ToolboxItem?displayProperty=nameWithType>
- `System.Resources.ResXNullRef`
- `System.Resources.ResXDataNode`
- `System.Resources.ResXFileRef`
- <xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>
- `System.Windows.Forms.NativeMethods.MSOCRINFOSTRUCT`
- `System.Windows.Forms.NativeMethods.MSG`

<span data-ttu-id="c34d3-105">Storicamente, questo meccanismo di serializzazione ha avuto seri problemi di manutenzione e sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c34d3-105">Historically, this serialization mechanism has had serious maintenance and security concerns.</span></span> <span data-ttu-id="c34d3-106">La `SerializableAttribute` gestione dei tipi significa che tali tipi devono essere testati per le modifiche di serializzazione da una versione a una versione e potenzialmente modifiche di serializzazione da framework a framework.</span><span class="sxs-lookup"><span data-stu-id="c34d3-106">Maintaining `SerializableAttribute` on types means those types must be tested for version-to-version serialization changes and potentially framework-to-framework serialization changes.</span></span> <span data-ttu-id="c34d3-107">Questo rende più difficile l'evoluzione di questi tipi e può essere costoso da mantenere.</span><span class="sxs-lookup"><span data-stu-id="c34d3-107">This makes it harder to evolve those types and can be costly to maintain.</span></span> <span data-ttu-id="c34d3-108">Questi tipi non hanno scenari di serializzazione binaria noti, che riduce al minimo l'impatto della rimozione dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="c34d3-108">These types have no known binary serialization scenarios, which minimizes the impact of removing the attribute.</span></span>

<span data-ttu-id="c34d3-109">Per ulteriori informazioni, vedere [Serializzazione binaria](~/docs/standard/serialization/binary-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="c34d3-109">For more information, see [Binary serialization](~/docs/standard/serialization/binary-serialization.md).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c34d3-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="c34d3-110">Version introduced</span></span>

<span data-ttu-id="c34d3-111">3.0 Anteprima 9</span><span class="sxs-lookup"><span data-stu-id="c34d3-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c34d3-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="c34d3-112">Recommended action</span></span>

<span data-ttu-id="c34d3-113">Aggiornare il codice che può dipendere da questi tipi contrassegnati come serializzabili.</span><span class="sxs-lookup"><span data-stu-id="c34d3-113">Update any code that may depend on these types being marked as serializable.</span></span>

#### <a name="category"></a><span data-ttu-id="c34d3-114">Category</span><span class="sxs-lookup"><span data-stu-id="c34d3-114">Category</span></span>

<span data-ttu-id="c34d3-115">Windows Form</span><span class="sxs-lookup"><span data-stu-id="c34d3-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c34d3-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="c34d3-116">Affected APIs</span></span>

- <span data-ttu-id="c34d3-117">nessuno</span><span class="sxs-lookup"><span data-stu-id="c34d3-117">None</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
