---
ms.openlocfilehash: d25c14f93da5fe8acf06269554fed30ddc6bc95d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614505"
---
### <a name="operationcontextcurrent-may-return-null-when-called-in-a-using-clause"></a><span data-ttu-id="02e26-101">OperationContext.Current può restituire Null in caso di chiamata in una clausola using</span><span class="sxs-lookup"><span data-stu-id="02e26-101">OperationContext.Current may return null when called in a using clause</span></span>

#### <a name="details"></a><span data-ttu-id="02e26-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="02e26-102">Details</span></span>

<span data-ttu-id="02e26-103"><xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> può restituire `null` e può essere generata un'eccezione <xref:System.NullReferenceException> se vengono soddisfatte tutte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="02e26-103"><xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> may return `null` and a <xref:System.NullReferenceException> may result if all of the following conditions are true:</span></span>

- <span data-ttu-id="02e26-104">Si recupera il valore della proprietà <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> in un metodo che restituisce <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="02e26-104">You retrieve the value of the <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> property in a method that returns a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span>
- <span data-ttu-id="02e26-105">Si crea un'istanza dell'oggetto <xref:System.ServiceModel.OperationContextScope> in una clausola `using`.</span><span class="sxs-lookup"><span data-stu-id="02e26-105">You instantiate the <xref:System.ServiceModel.OperationContextScope> object in a `using` clause.</span></span>
- <span data-ttu-id="02e26-106">Si recupera il valore della proprietà <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> all'interno di `using statement`.</span><span class="sxs-lookup"><span data-stu-id="02e26-106">You retrieve the value of the <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> property within the `using statement`.</span></span> <span data-ttu-id="02e26-107">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="02e26-107">For example:</span></span>

```csharp
using (new OperationContextScope(OperationContext.Current))
{
    // OperationContext.Current is null.
    OperationContext context = OperationContext.Current;

    // ...
}
```

#### <a name="suggestion"></a><span data-ttu-id="02e26-108">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="02e26-108">Suggestion</span></span>

<span data-ttu-id="02e26-109">Per risolvere questo problema, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="02e26-109">To address this issue, you can do the following:</span></span>

- <span data-ttu-id="02e26-110">Modificare il codice come indicato di seguito per creare un'istanza di un nuovo `null` <xref:System.ServiceModel.OperationContext.Current%2A> oggetto non:</span><span class="sxs-lookup"><span data-stu-id="02e26-110">Modify your code as follows to instantiate a new non- `null` <xref:System.ServiceModel.OperationContext.Current%2A> object:</span></span>

    ```csharp
    OperationContext ocx = OperationContext.Current;
    using (new OperationContextScope(OperationContext.Current))
    {
        OperationContext.Current = new OperationContext(ocx.Channel);

        // ...
    }
    ```

- <span data-ttu-id="02e26-111">Installare l'aggiornamento più recente di .NET Framework 4.6.2 oppure eseguire l'aggiornamento a una versione successiva di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="02e26-111">Install the latest update to the .NET Framework 4.6.2, or upgrade to a later version of the .NET Framework.</span></span> <span data-ttu-id="02e26-112">Viene così disabilitato il flusso di <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> e ripristinato il comportamento delle applicazioni WCF in .NET Framework 4.6.1 e versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="02e26-112">This disables the flow of the <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> and restores the behavior of WCF applications in the .NET Framework 4.6.1 and earlier versions.</span></span> <span data-ttu-id="02e26-113">Questo comportamento è configurabile ed è equivalente all'aggiunta dell'impostazione dell'app seguente nel file di configurazione:</span><span class="sxs-lookup"><span data-stu-id="02e26-113">This behavior is configurable; it is equivalent to adding the following app setting to your configuration file:</span></span>

    ```xml
    <appSettings>
      <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
    </appSettings>
    ```

    <span data-ttu-id="02e26-114">Se questa modifica non è opportuna e l'applicazione dipende dal flusso del contesto di esecuzione tra i contesti operativi, è possibile abilitare il flusso come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="02e26-114">If this change is undesirable and your application depends on execution context flowing between operation contexts, you can enable its flow as follows:</span></span>

    ```xml
    <appSettings>
      <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="false" />
    </appSettings>
    ```

| <span data-ttu-id="02e26-115">Nome</span><span class="sxs-lookup"><span data-stu-id="02e26-115">Name</span></span>    | <span data-ttu-id="02e26-116">Valore</span><span class="sxs-lookup"><span data-stu-id="02e26-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="02e26-117">Scope</span><span class="sxs-lookup"><span data-stu-id="02e26-117">Scope</span></span>   | <span data-ttu-id="02e26-118">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="02e26-118">Edge</span></span>        |
| <span data-ttu-id="02e26-119">Version</span><span class="sxs-lookup"><span data-stu-id="02e26-119">Version</span></span> | <span data-ttu-id="02e26-120">4.6.2</span><span class="sxs-lookup"><span data-stu-id="02e26-120">4.6.2</span></span>       |
| <span data-ttu-id="02e26-121">Type</span><span class="sxs-lookup"><span data-stu-id="02e26-121">Type</span></span>    | <span data-ttu-id="02e26-122">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="02e26-122">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="02e26-123">API interessate</span><span class="sxs-lookup"><span data-stu-id="02e26-123">Affected APIs</span></span>

- <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>
