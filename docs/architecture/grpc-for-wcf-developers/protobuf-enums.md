---
title: Enumerazioni Protobuf - gRPC per gli sviluppatori WCFProtobuf enumerations - gRPC for WCF developers
description: Scopri come dichiarare e usare le enumerazioni in Protobuf.
ms.date: 09/09/2019
ms.openlocfilehash: 2177f568a671fa0e651625c6e025ac70c243feb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148075"
---
# <a name="protobuf-enumerations"></a><span data-ttu-id="2e9c4-103">Enumerazioni protobuf</span><span class="sxs-lookup"><span data-stu-id="2e9c4-103">Protobuf enumerations</span></span>

<span data-ttu-id="2e9c4-104">Protobuf supporta i tipi di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="2e9c4-104">Protobuf supports enumeration types.</span></span> <span data-ttu-id="2e9c4-105">Questo supporto è stato illustrato nella sezione precedente, in cui `Oneof` è stata utilizzata un'enumerazione per determinare il tipo di un campo.</span><span class="sxs-lookup"><span data-stu-id="2e9c4-105">You saw this support in the previous section, where an enum was used to determine the type of a `Oneof` field.</span></span> <span data-ttu-id="2e9c4-106">È possibile definire i propri tipi di enumerazione e Protobuf li compilerà in tipi enum c'è.</span><span class="sxs-lookup"><span data-stu-id="2e9c4-106">You can define your own enumeration types, and Protobuf will compile them to C# enum types.</span></span>

<span data-ttu-id="2e9c4-107">Poiché è possibile usare Protobuf con vari linguaggi, le convenzioni di denominazione per le enumerazioni sono diverse dalle convenzioni di C.</span><span class="sxs-lookup"><span data-stu-id="2e9c4-107">Because you can use Protobuf with various languages, the naming conventions for enumerations are different from the C# conventions.</span></span> <span data-ttu-id="2e9c4-108">Tuttavia, il generatore di codice converte i nomi nel caso tradizionale di C .</span><span class="sxs-lookup"><span data-stu-id="2e9c4-108">However, the code generator converts the names to the traditional C# case.</span></span> <span data-ttu-id="2e9c4-109">Se l'equivalente in caso di maiuscole e minuscole Pascal del nome del campo inizia con il nome dell'enumerazione, viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="2e9c4-109">If the Pascal-case equivalent of the field name starts with the enumeration name, then it's removed.</span></span>

<span data-ttu-id="2e9c4-110">Ad esempio, nell'enumerazione Protobuf seguente, `ACCOUNT_STATUS`i campi sono preceduti da .</span><span class="sxs-lookup"><span data-stu-id="2e9c4-110">For example, in the following Protobuf enumeration, the fields are prefixed with `ACCOUNT_STATUS`.</span></span> <span data-ttu-id="2e9c4-111">Questo prefisso è equivalente al nome `AccountStatus`dell'enumerazione pascal-case, .</span><span class="sxs-lookup"><span data-stu-id="2e9c4-111">This prefix is equivalent to the Pascal-case enum name, `AccountStatus`.</span></span>

```protobuf
enum AccountStatus {
  ACCOUNT_STATUS_UNKNOWN = 0;
  ACCOUNT_STATUS_PENDING = 1;
  ACCOUNT_STATUS_ACTIVE = 2;
  ACCOUNT_STATUS_SUSPENDED = 3;
  ACCOUNT_STATUS_CLOSED = 4;
}
```

<span data-ttu-id="2e9c4-112">Il generatore consente di creare un'enumerazione di C' equivalente al codice seguente:The generator creates a C' enum equivalent to the following code:</span><span class="sxs-lookup"><span data-stu-id="2e9c4-112">The generator creates a C# enum equivalent to the following code:</span></span>

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

<span data-ttu-id="2e9c4-113">Le definizioni di enumerazione Protobuf *devono* avere una costante zero come primo campo.</span><span class="sxs-lookup"><span data-stu-id="2e9c4-113">Protobuf enumeration definitions *must* have a zero constant as their first field.</span></span> <span data-ttu-id="2e9c4-114">Come in C, è possibile dichiarare più campi con lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="2e9c4-114">As in C#, you can declare multiple fields with the same value.</span></span> <span data-ttu-id="2e9c4-115">Ma è necessario abilitare in `allow_alias` modo esplicito questa opzione utilizzando l'opzione nell'enumerazione:</span><span class="sxs-lookup"><span data-stu-id="2e9c4-115">But you must explicitly enable this option by using the `allow_alias` option in the enum:</span></span>

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

<span data-ttu-id="2e9c4-116">È possibile dichiarare le enumerazioni `.proto` al livello superiore in un file o annidate all'interno di una definizione di messaggio.</span><span class="sxs-lookup"><span data-stu-id="2e9c4-116">You can declare enumerations at the top level in a `.proto` file, or nested within a message definition.</span></span> <span data-ttu-id="2e9c4-117">Le enumerazioni annidate, come i `.Types` messaggi annidati, verranno dichiarate all'interno della classe statica nella classe messaggio generata.</span><span class="sxs-lookup"><span data-stu-id="2e9c4-117">Nested enumerations—like nested messages—will be declared within the `.Types` static class in the generated message class.</span></span>

<span data-ttu-id="2e9c4-118">Non è possibile applicare l'attributo [[Flags]](xref:System.FlagsAttribute) a un'enumerazione generata da Protobuf e Protobuf non comprende le combinazioni di enumerazioni bit per bit.</span><span class="sxs-lookup"><span data-stu-id="2e9c4-118">There's no way to apply the [[Flags]](xref:System.FlagsAttribute) attribute to a Protobuf-generated enum, and Protobuf doesn't understand bitwise enum combinations.</span></span> <span data-ttu-id="2e9c4-119">Guardate l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="2e9c4-119">Look at the following example:</span></span>

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

<span data-ttu-id="2e9c4-120">Se si `product.AvailableIn` `Region.NorthAmerica | Region.SouthAmerica`imposta su , viene serializzato `3`come valore intero .</span><span class="sxs-lookup"><span data-stu-id="2e9c4-120">If you set `product.AvailableIn` to `Region.NorthAmerica | Region.SouthAmerica`, it's serialized as the integer value `3`.</span></span> <span data-ttu-id="2e9c4-121">Quando un client o un server tenta di deserializzare il valore, `3`non troverà una corrispondenza nella definizione di enumerazione per .</span><span class="sxs-lookup"><span data-stu-id="2e9c4-121">When a client or server tries to deserialize the value, it won't find a match in the enum definition for `3`.</span></span> <span data-ttu-id="2e9c4-122">Il risultato `Region.None`sarà .</span><span class="sxs-lookup"><span data-stu-id="2e9c4-122">The result will be `Region.None`.</span></span>

<span data-ttu-id="2e9c4-123">Il modo migliore per lavorare con più valori di enumerazione in Protobuf consiste nell'utilizzare un `repeated` campo del tipo enum.</span><span class="sxs-lookup"><span data-stu-id="2e9c4-123">The best way to work with multiple enum values in Protobuf is to use a `repeated` field of the enum type.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2e9c4-124">[Successivo](protobuf-any-oneof.md)
>[precedente](protobuf-maps.md)</span><span class="sxs-lookup"><span data-stu-id="2e9c4-124">[Previous](protobuf-any-oneof.md)
[Next](protobuf-maps.md)</span></span>
