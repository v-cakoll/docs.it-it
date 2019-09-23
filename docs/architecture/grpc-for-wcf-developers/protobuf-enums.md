---
title: Enumerazioni protobuf-gRPC per sviluppatori WCF
description: Informazioni su come dichiarare e usare le enumerazioni in protobuf.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: d93319b713588129a19246976a82bb03a90ce680
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184239"
---
# <a name="protobuf-enumerations"></a><span data-ttu-id="850c9-103">Enumerazioni protobuf</span><span class="sxs-lookup"><span data-stu-id="850c9-103">Protobuf enumerations</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="850c9-104">Protobuf supporta i tipi di enumerazione, come illustrato nella sezione precedente, in cui è stata usata un'enumerazione per determinare `oneof` il tipo di un campo.</span><span class="sxs-lookup"><span data-stu-id="850c9-104">Protobuf supports enumeration types, as seen in the previous section where an enum was used to determine the type of a `oneof` field.</span></span> <span data-ttu-id="850c9-105">È possibile definire tipi di enumerazione personalizzati e protobuf li compilerà C# ai tipi enum.</span><span class="sxs-lookup"><span data-stu-id="850c9-105">You can define your own enumeration types and Protobuf will compile them to C# enum types.</span></span> <span data-ttu-id="850c9-106">Poiché protobuf può essere usato con lingue diverse, le convenzioni di denominazione per le enumerazioni sono C# diverse dalle convenzioni.</span><span class="sxs-lookup"><span data-stu-id="850c9-106">Since Protobuf can be used with different languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="850c9-107">Tuttavia, il generatore di codice è intelligente e converte i nomi nel caso C# tradizionale.</span><span class="sxs-lookup"><span data-stu-id="850c9-107">However, the code generator is clever and converts the names to the traditional C# case.</span></span> <span data-ttu-id="850c9-108">Se l'equivalente del case Pascal del nome del campo inizia con il nome dell'enumerazione, viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="850c9-108">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="850c9-109">Ad esempio, in questa enumerazione protobuf i campi sono preceduti `ACCOUNT_STATUS`da, che equivale al nome enum del case Pascal:. `AccountStatus`</span><span class="sxs-lookup"><span data-stu-id="850c9-109">For example, in this Protobuf enumeration the fields are prefixed with `ACCOUNT_STATUS`, which is equivalent to the Pascal case enum name: `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="850c9-110">Il generatore crea quindi un' C# enumerazione equivalente al codice seguente:</span><span class="sxs-lookup"><span data-stu-id="850c9-110">So, the generator creates a C# enum equivalent to the following code:</span></span>

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

<span data-ttu-id="850c9-111">Le definizioni di enumerazione protobuf **devono** avere una costante zero come primo campo.</span><span class="sxs-lookup"><span data-stu-id="850c9-111">Protobuf enumeration definitions **must** have a zero constant as their first field.</span></span> <span data-ttu-id="850c9-112">Come in C#, è possibile dichiarare più campi con lo stesso valore, ma è necessario abilitare in modo esplicito questa opzione `allow_alias` usando l'opzione nell'enumerazione:</span><span class="sxs-lookup"><span data-stu-id="850c9-112">As in C#, you can declare multiple fields with the same value, but you must explicitly enable this option using the `allow_alias` option in the enum:</span></span>

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

<span data-ttu-id="850c9-113">È possibile dichiarare Enumerazioni al primo livello in un `.proto` file o annidate all'interno di una definizione di messaggio.</span><span class="sxs-lookup"><span data-stu-id="850c9-113">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="850c9-114">Le enumerazioni annidate, ad esempio i messaggi annidati, `.Types` verranno dichiarate all'interno della classe statica nella classe Message generata.</span><span class="sxs-lookup"><span data-stu-id="850c9-114">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="850c9-115">Non è possibile applicare l'attributo [[flags]](xref:System.FlagsAttribute) a un'enumerazione generata da protobuf e protobuf non riconosce le combinazioni di enumerazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="850c9-115">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="850c9-116">Esaminare l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="850c9-116">Take a look at the following example:</span></span>

```protobuf
enum Region {
  REGION_NONE = 0;
  REGION_NORTH_AMERICA = 1;
  REGION_SOUTH_AMERICA = 2;
  REGION_EMEA = 4;
  REGION_APAC = 8;
}

message Product {
  Region availableIn = 1;
}
```

<span data-ttu-id="850c9-117">Se si imposta `product.AvailableIn` su `Region.NorthAmerica | Region.SouthAmerica`, viene serializzato come valore `3`Integer.</span><span class="sxs-lookup"><span data-stu-id="850c9-117">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="850c9-118">Quando un client o un server tenta di deserializzare il valore, non troverà una corrispondenza nella definizione di enumerazione per `3` e il risultato `Region.None`sarà.</span><span class="sxs-lookup"><span data-stu-id="850c9-118">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3` and the result will be `Region.None`.</span></span>

<span data-ttu-id="850c9-119">Il modo migliore per lavorare con più valori enum in protobuf consiste nell'usare un `repeated` campo di tipo enum.</span><span class="sxs-lookup"><span data-stu-id="850c9-119">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="850c9-120">[Precedente](protobuf-any-oneof.md)
>[Successivo](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="850c9-120">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>
