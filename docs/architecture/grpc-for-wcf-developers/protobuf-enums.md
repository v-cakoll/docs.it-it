---
title: Enumerazioni protobuf-gRPC per sviluppatori WCF
description: Informazioni su come dichiarare e usare le enumerazioni in protobuf.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: f18196f54caba824d7101782a88cf3bf699560d5
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846347"
---
# <a name="protobuf-enumerations"></a><span data-ttu-id="5aafb-103">Enumerazioni protobuf</span><span class="sxs-lookup"><span data-stu-id="5aafb-103">Protobuf enumerations</span></span>

<span data-ttu-id="5aafb-104">Protobuf supporta i tipi di enumerazione, come illustrato nella sezione precedente, in cui è stata usata un'enumerazione per determinare il tipo di un campo `oneof`.</span><span class="sxs-lookup"><span data-stu-id="5aafb-104">Protobuf supports enumeration types, as seen in the previous section where an enum was used to determine the type of a `oneof` field.</span></span> <span data-ttu-id="5aafb-105">È possibile definire tipi di enumerazione personalizzati e protobuf li compilerà C# ai tipi enum.</span><span class="sxs-lookup"><span data-stu-id="5aafb-105">You can define your own enumeration types and Protobuf will compile them to C# enum types.</span></span> <span data-ttu-id="5aafb-106">Poiché protobuf può essere usato con lingue diverse, le convenzioni di denominazione per le enumerazioni sono C# diverse dalle convenzioni.</span><span class="sxs-lookup"><span data-stu-id="5aafb-106">Since Protobuf can be used with different languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="5aafb-107">Tuttavia, il generatore di codice è intelligente e converte i nomi nel caso C# tradizionale.</span><span class="sxs-lookup"><span data-stu-id="5aafb-107">However, the code generator is clever and converts the names to the traditional C# case.</span></span> <span data-ttu-id="5aafb-108">Se l'equivalente del case Pascal del nome del campo inizia con il nome dell'enumerazione, viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="5aafb-108">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="5aafb-109">Ad esempio, in questa enumerazione protobuf i campi sono preceduti da `ACCOUNT_STATUS`, che equivale al nome enum del case Pascal: `AccountStatus`.</span><span class="sxs-lookup"><span data-stu-id="5aafb-109">For example, in this Protobuf enumeration the fields are prefixed with `ACCOUNT_STATUS`, which is equivalent to the Pascal case enum name: `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="5aafb-110">Il generatore crea quindi un' C# enumerazione equivalente al codice seguente:</span><span class="sxs-lookup"><span data-stu-id="5aafb-110">So, the generator creates a C# enum equivalent to the following code:</span></span>

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

<span data-ttu-id="5aafb-111">Le definizioni di enumerazione protobuf **devono** avere una costante zero come primo campo.</span><span class="sxs-lookup"><span data-stu-id="5aafb-111">Protobuf enumeration definitions **must** have a zero constant as their first field.</span></span> <span data-ttu-id="5aafb-112">Come in C#, è possibile dichiarare più campi con lo stesso valore, ma è necessario abilitare questa opzione in modo esplicito tramite l'opzione`allow_alias`nell'enumerazione:</span><span class="sxs-lookup"><span data-stu-id="5aafb-112">As in C#, you can declare multiple fields with the same value, but you must explicitly enable this option using the `allow_alias` option in the enum:</span></span>

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

<span data-ttu-id="5aafb-113">È possibile dichiarare Enumerazioni al livello principale in un file di `.proto` o annidate all'interno di una definizione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="5aafb-113">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="5aafb-114">Le enumerazioni annidate, ad esempio i messaggi annidati, verranno dichiarate all'interno della classe statica `.Types` nella classe messaggio generata.</span><span class="sxs-lookup"><span data-stu-id="5aafb-114">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="5aafb-115">Non è possibile applicare l'attributo [[flags]](xref:System.FlagsAttribute) a un'enumerazione generata da protobuf e protobuf non riconosce le combinazioni di enumerazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="5aafb-115">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="5aafb-116">Esaminare l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="5aafb-116">Take a look at the following example:</span></span>

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

<span data-ttu-id="5aafb-117">Se si imposta `product.AvailableIn` su `Region.NorthAmerica | Region.SouthAmerica`, questo viene serializzato come valore integer `3`.</span><span class="sxs-lookup"><span data-stu-id="5aafb-117">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="5aafb-118">Quando un client o un server tenta di deserializzare il valore, non troverà una corrispondenza nella definizione di enumerazione per `3` e il risultato verrà `Region.None`.</span><span class="sxs-lookup"><span data-stu-id="5aafb-118">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3` and the result will be `Region.None`.</span></span>

<span data-ttu-id="5aafb-119">Il modo migliore per lavorare con più valori enum in protobuf consiste nell'usare un campo `repeated` di tipo enum.</span><span class="sxs-lookup"><span data-stu-id="5aafb-119">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5aafb-120">[Precedente](protobuf-any-oneof.md)
>[Successivo](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="5aafb-120">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>
