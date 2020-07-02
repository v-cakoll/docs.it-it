---
ms.openlocfilehash: c462c7b4ec8423ce8fd331d3cd31154283cf1f1d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620261"
---
### <a name="marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a><span data-ttu-id="84ffc-101">Gli overload Marshal.SizeOf and Marshal.PtrToStructure causano interruzioni del codice dinamico</span><span class="sxs-lookup"><span data-stu-id="84ffc-101">Marshal.SizeOf and Marshal.PtrToStructure overloads break dynamic code</span></span>

#### <a name="details"></a><span data-ttu-id="84ffc-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="84ffc-102">Details</span></span>

<span data-ttu-id="84ffc-103">A partire da .NET Framework 4.5.1, l'associazione dinamica per i metodi <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601>, <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601(%60%600)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Object)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Type)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr)> o <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr,%60%600)> (ad esempio, tramite Windows PowerShell, IronPython o la parola chiave dynamic di C#) può causare eccezioni <code>MethodInvocationExceptions</code> perché sono stati aggiunti nuovi overload di questi metodi che potrebbero risultare ambigui per i motori di script.</span><span class="sxs-lookup"><span data-stu-id="84ffc-103">Beginning in the .NET Framework 4.5.1, dynamically binding to the methods <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601>, <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601(%60%600)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Object)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Type)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr)>, or <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr,%60%600)>, (via Windows PowerShell, IronPython, or the C# dynamic keyword, for example) can result in <code>MethodInvocationExceptions</code> because new overloads of these methods have been added that may be ambiguous to the scripting engines.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="84ffc-104">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="84ffc-104">Suggestion</span></span>

<span data-ttu-id="84ffc-105">Aggiornare gli script per indicare chiaramente quale overload deve essere usato.</span><span class="sxs-lookup"><span data-stu-id="84ffc-105">Update scripts to clearly indicate which overload should be used.</span></span> <span data-ttu-id="84ffc-106">Questa operazione può essere eseguita in genere tramite il cast esplicito dei parametri di tipo dei metodi su <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="84ffc-106">This can typically done by explicitly casting the methods' type parameters as <xref:System.Type>.</span></span> <span data-ttu-id="84ffc-107">Vedere [questo collegamento](https://support.microsoft.com/kb/2909958/) per altri dettagli ed esempi per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="84ffc-107">See [this link](https://support.microsoft.com/kb/2909958/) for more detail and examples of how to workaround the issue.</span></span>

| <span data-ttu-id="84ffc-108">Nome</span><span class="sxs-lookup"><span data-stu-id="84ffc-108">Name</span></span>    | <span data-ttu-id="84ffc-109">Valore</span><span class="sxs-lookup"><span data-stu-id="84ffc-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="84ffc-110">Scope</span><span class="sxs-lookup"><span data-stu-id="84ffc-110">Scope</span></span>   |<span data-ttu-id="84ffc-111">Minorenne</span><span class="sxs-lookup"><span data-stu-id="84ffc-111">Minor</span></span>|
|<span data-ttu-id="84ffc-112">Version</span><span class="sxs-lookup"><span data-stu-id="84ffc-112">Version</span></span>|<span data-ttu-id="84ffc-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="84ffc-113">4.5.1</span></span>|
|<span data-ttu-id="84ffc-114">Type</span><span class="sxs-lookup"><span data-stu-id="84ffc-114">Type</span></span>|<span data-ttu-id="84ffc-115">Runtime</span><span class="sxs-lookup"><span data-stu-id="84ffc-115">Runtime</span></span>|
