---
title: Enumerazioni protobuf-gRPC per sviluppatori WCF
description: Informazioni su come dichiarare e usare le enumerazioni in protobuf.
ms.date: 09/09/2019
ms.openlocfilehash: 01cf4a4e5e0eda1e7ddff2a6780119fcb3120dad
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543144"
---
# <a name="protobuf-enumerations"></a><span data-ttu-id="d2634-103">Enumerazioni protobuf</span><span class="sxs-lookup"><span data-stu-id="d2634-103">Protobuf enumerations</span></span>

<span data-ttu-id="d2634-104">Protobuf supporta i tipi di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="d2634-104">Protobuf supports enumeration types.</span></span> <span data-ttu-id="d2634-105">Questo supporto è stato visualizzato nella sezione precedente, in cui è stata usata un'enumerazione per determinare il tipo di un campo di `Oneof`.</span><span class="sxs-lookup"><span data-stu-id="d2634-105">You saw this support in the previous section, where an enum was used to determine the type of a `Oneof` field.</span></span> <span data-ttu-id="d2634-106">È possibile definire tipi di enumerazione personalizzati e protobuf li compilerà ai C# tipi enum.</span><span class="sxs-lookup"><span data-stu-id="d2634-106">You can define your own enumeration types, and Protobuf will compile them to C# enum types.</span></span> 

<span data-ttu-id="d2634-107">Poiché è possibile utilizzare protobuf con diversi linguaggi, le convenzioni di denominazione per le enumerazioni sono C# diverse dalle convenzioni.</span><span class="sxs-lookup"><span data-stu-id="d2634-107">Because you can use Protobuf with various languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="d2634-108">Tuttavia, il generatore di codice converte i nomi nel caso C# tradizionale.</span><span class="sxs-lookup"><span data-stu-id="d2634-108">However, the code generator converts the names to the traditional C# case.</span></span> <span data-ttu-id="d2634-109">Se l'equivalente del case Pascal del nome del campo inizia con il nome dell'enumerazione, viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="d2634-109">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="d2634-110">Nell'enumerazione protobuf seguente, ad esempio, i campi sono preceduti dal prefisso `ACCOUNT_STATUS`.</span><span class="sxs-lookup"><span data-stu-id="d2634-110">For example, in the following Protobuf enumeration, the fields are prefixed with `ACCOUNT_STATUS`.</span></span> <span data-ttu-id="d2634-111">Questo prefisso è equivalente al nome dell'enumerazione del case Pascal, `AccountStatus`.</span><span class="sxs-lookup"><span data-stu-id="d2634-111">This prefix is equivalent to the Pascal-case enum name, `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="d2634-112">Il generatore crea un' C# enumerazione equivalente al codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d2634-112">The generator creates a C# enum equivalent to the following code:</span></span>

```csharp
public enum AccountStatus
{
    Unknown = 0,
    Pending = 1,
    Active = 2,
    Suspended = 3,
    Closed = 4
}
```

<span data-ttu-id="d2634-113">Le definizioni di enumerazione protobuf *devono* avere una costante zero come primo campo.</span><span class="sxs-lookup"><span data-stu-id="d2634-113">Protobuf enumeration definitions *must* have a zero constant as their first field.</span></span> <span data-ttu-id="d2634-114">Come in C#, è possibile dichiarare più campi con lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="d2634-114">As in C#, you can declare multiple fields with the same value.</span></span> <span data-ttu-id="d2634-115">Tuttavia, è necessario abilitare questa opzione in modo esplicito tramite l'opzione `allow_alias` nell'enumerazione:</span><span class="sxs-lookup"><span data-stu-id="d2634-115">But you must explicitly enable this option by using the `allow_alias` option in the enum:</span></span>

```protobuf
enum AccountStatus {
  option allow_alias = true;
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
  ACCOUNT_STATUS_CANCELLED = 4;
}
```

<span data-ttu-id="d2634-116">È possibile dichiarare Enumerazioni al livello principale in un file di `.proto` o annidate all'interno di una definizione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d2634-116">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="d2634-117">Le enumerazioni annidate, ad esempio i messaggi annidati, verranno dichiarate all'interno della classe statica `.Types` nella classe messaggio generata.</span><span class="sxs-lookup"><span data-stu-id="d2634-117">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="d2634-118">Non è possibile applicare l'attributo [[flags]](xref:System.FlagsAttribute) a un'enumerazione generata da protobuf e protobuf non riconosce le combinazioni di enumerazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="d2634-118">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="d2634-119">Esaminare l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="d2634-119">Look at the following example:</span></span>

```protobuf
enum Region {
  REGION_NONE = 0;
  REGION_NORTH_AMERICA = 1;
  REGION_SOUTH_AMERICA = 2;
  REGION_EMEA = 4;
  REGION_APAC = 8;
}

message Product {
  Region available_in = 1;
}
```

<span data-ttu-id="d2634-120">Se si imposta `product.AvailableIn` su `Region.NorthAmerica | Region.SouthAmerica`, questo viene serializzato come valore integer `3`.</span><span class="sxs-lookup"><span data-stu-id="d2634-120">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="d2634-121">Quando un client o un server tenta di deserializzare il valore, non troverà una corrispondenza nella definizione di enumerazione per `3`.</span><span class="sxs-lookup"><span data-stu-id="d2634-121">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3`.</span></span> <span data-ttu-id="d2634-122">Il risultato sarà `Region.None`.</span><span class="sxs-lookup"><span data-stu-id="d2634-122">The result will be `Region.None`.</span></span>

<span data-ttu-id="d2634-123">Il modo migliore per lavorare con più valori enum in protobuf consiste nell'usare un campo `repeated` di tipo enum.</span><span class="sxs-lookup"><span data-stu-id="d2634-123">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d2634-124">[Precedente](protobuf-any-oneof.md)
>[Successivo](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="d2634-124">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>
