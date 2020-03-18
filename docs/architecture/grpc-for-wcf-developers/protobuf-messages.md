---
title: Messaggi di protobuf - gRPC per gli sviluppatori WCFProtobuf messages - gRPC for WCF developers
description: Scopri come i messaggi Protobuf vengono definiti nel file IDL e generati in C.
ms.date: 09/09/2019
ms.openlocfilehash: 5b3d4383de39a3785ef804fec21939a740f54669
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147984"
---
# <a name="protobuf-messages"></a><span data-ttu-id="3f63a-103">Messaggi protobuf</span><span class="sxs-lookup"><span data-stu-id="3f63a-103">Protobuf messages</span></span>

<span data-ttu-id="3f63a-104">In questa sezione viene illustrato come dichiarare i `.proto` messaggi del buffer di protocollo (Protobuf) nei file.</span><span class="sxs-lookup"><span data-stu-id="3f63a-104">This section covers how to declare Protocol Buffer (Protobuf) messages in `.proto` files.</span></span> <span data-ttu-id="3f63a-105">Vengono illustrati i concetti fondamentali dei tipi e numeri di campo `protoc` e vengono esaminato il codice c'è generato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="3f63a-105">It explains the fundamental concepts of field numbers and types, and it looks at the C# code that the `protoc` compiler generates.</span></span>

<span data-ttu-id="3f63a-106">Il resto del capitolo esaminerà più in dettaglio come i diversi tipi di dati sono rappresentati in Protobuf.</span><span class="sxs-lookup"><span data-stu-id="3f63a-106">The rest of the chapter will look in more detail at how different types of data are represented in Protobuf.</span></span>

## <a name="declaring-a-message"></a><span data-ttu-id="3f63a-107">Dichiarazione di un messaggioDeclaring a message</span><span class="sxs-lookup"><span data-stu-id="3f63a-107">Declaring a message</span></span>

<span data-ttu-id="3f63a-108">In Windows Communication Foundation `Stock` (WCF), una classe per un'applicazione di trading sul mercato azionario potrebbe essere definita come nell'esempio seguente:In Windows Communication Foundation (WCF), a class for a stock market market trading application might be defined like the following example:</span><span class="sxs-lookup"><span data-stu-id="3f63a-108">In Windows Communication Foundation (WCF), a `Stock` class for a stock market trading application might be defined like the following example:</span></span>

```csharp
namespace TraderSys
{
    [DataContract]
    public class Stock
    {
        [DataMember]
        public int Id { get; set;}
        [DataMember]
        public string Symbol { get; set;}
        [DataMember]
        public string DisplayName { get; set;}
        [DataMember]
        public int MarketId { get; set; }
    }
}
```

<span data-ttu-id="3f63a-109">Per implementare la classe equivalente in Protobuf, è necessario dichiararla nel `.proto` file.</span><span class="sxs-lookup"><span data-stu-id="3f63a-109">To implement the equivalent class in Protobuf, you must declare it in the `.proto` file.</span></span> <span data-ttu-id="3f63a-110">Il `protoc` compilatore genererà quindi la classe .NET come parte del processo di compilazione.</span><span class="sxs-lookup"><span data-stu-id="3f63a-110">The `protoc` compiler will then generate the .NET class as part of the build process.</span></span>

```protobuf
syntax "proto3";

option csharp_namespace = "TraderSys";

message Stock {

    int32 id = 1;
    string symbol = 2;
    string display_name = 3;
    int32 market_id = 4;

}  
```

<span data-ttu-id="3f63a-111">La prima riga dichiara la versione della sintassi in uso.</span><span class="sxs-lookup"><span data-stu-id="3f63a-111">The first line declares the syntax version being used.</span></span> <span data-ttu-id="3f63a-112">La versione 3 della lingua è stata rilasciata nel 2016.</span><span class="sxs-lookup"><span data-stu-id="3f63a-112">Version 3 of the language was released in 2016.</span></span> <span data-ttu-id="3f63a-113">È la versione che consigliamo per i servizi gRPC.</span><span class="sxs-lookup"><span data-stu-id="3f63a-113">It's the version that we recommend for gRPC services.</span></span>

<span data-ttu-id="3f63a-114">La `option csharp_namespace` riga specifica lo spazio dei nomi da utilizzare per i tipi C .</span><span class="sxs-lookup"><span data-stu-id="3f63a-114">The `option csharp_namespace` line specifies the namespace to be used for the generated C# types.</span></span> <span data-ttu-id="3f63a-115">Questa opzione verrà ignorata quando il `.proto` file viene compilato per altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="3f63a-115">This option will be ignored when the `.proto` file is compiled for other languages.</span></span> <span data-ttu-id="3f63a-116">I file Protobuf spesso contengono opzioni specifiche della lingua per diverse lingue.</span><span class="sxs-lookup"><span data-stu-id="3f63a-116">Protobuf files often contain language-specific options for several languages.</span></span>

<span data-ttu-id="3f63a-117">La `Stock` definizione del messaggio specifica quattro campi.</span><span class="sxs-lookup"><span data-stu-id="3f63a-117">The `Stock` message definition specifies four fields.</span></span> <span data-ttu-id="3f63a-118">Ognuno ha un tipo, un nome e un numero di campo.</span><span class="sxs-lookup"><span data-stu-id="3f63a-118">Each has a type, a name, and a field number.</span></span>

## <a name="field-numbers"></a><span data-ttu-id="3f63a-119">Numeri di campo</span><span class="sxs-lookup"><span data-stu-id="3f63a-119">Field numbers</span></span>

<span data-ttu-id="3f63a-120">I numeri di campo sono una parte importante di Protobuf.</span><span class="sxs-lookup"><span data-stu-id="3f63a-120">Field numbers are an important part of Protobuf.</span></span> <span data-ttu-id="3f63a-121">Vengono utilizzati per identificare i campi nei dati codificati binari, il che significa che non possono passare da una versione all'altro del servizio.</span><span class="sxs-lookup"><span data-stu-id="3f63a-121">They're used to identify fields in the binary encoded data, which means they can't change from version to version of your service.</span></span> <span data-ttu-id="3f63a-122">Il vantaggio è che la compatibilità con le versioni precedenti e la compatibilità in avanti sono possibili.</span><span class="sxs-lookup"><span data-stu-id="3f63a-122">The advantage is that backward compatibility and forward compatibility are possible.</span></span> <span data-ttu-id="3f63a-123">I client e i servizi ignoreranno semplicemente i numeri di campo che non conoscono, a condizione che venga gestita la possibilità di una gestione dei valori mancanti.</span><span class="sxs-lookup"><span data-stu-id="3f63a-123">Clients and services will simply ignore field numbers that they don't know about, as long as the possibility of missing values is handled.</span></span>

<span data-ttu-id="3f63a-124">Nel formato binario, il numero di campo viene combinato con un identificatore di tipo.</span><span class="sxs-lookup"><span data-stu-id="3f63a-124">In the binary format, the field number is combined with a type identifier.</span></span> <span data-ttu-id="3f63a-125">I numeri di campo da 1 a 15 possono essere codificati con il tipo come un singolo byte.</span><span class="sxs-lookup"><span data-stu-id="3f63a-125">Field numbers from 1 to 15 can be encoded with their type as a single byte.</span></span> <span data-ttu-id="3f63a-126">I numeri da 16 a 2.047 richiedono 2 byte.</span><span class="sxs-lookup"><span data-stu-id="3f63a-126">Numbers from 16 to 2,047 take 2 bytes.</span></span> <span data-ttu-id="3f63a-127">Si può andare più in alto se avete bisogno di più di 2.047 campi su un messaggio per qualsiasi motivo.</span><span class="sxs-lookup"><span data-stu-id="3f63a-127">You can go higher if you need more than 2,047 fields on a message for any reason.</span></span> <span data-ttu-id="3f63a-128">Gli identificatori a byte singolo per i numeri di campo da 1 a 15 offrono prestazioni migliori, pertanto è consigliabile utilizzarli per i campi più semplici e utilizzati di frequente.</span><span class="sxs-lookup"><span data-stu-id="3f63a-128">The single byte identifiers for field numbers 1 to 15 offer better performance, so you should use them for the most basic, frequently used fields.</span></span>

## <a name="types"></a><span data-ttu-id="3f63a-129">Tipi</span><span class="sxs-lookup"><span data-stu-id="3f63a-129">Types</span></span>

<span data-ttu-id="3f63a-130">Le dichiarazioni dei tipi utilizzano i tipi di dati scalari nativi di Protobuf, descritti in modo più dettagliato [nella sezione successiva.](protobuf-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="3f63a-130">The type declarations are using Protobuf's native scalar data types, which are discussed in more detail in [the next section](protobuf-data-types.md).</span></span> <span data-ttu-id="3f63a-131">Il resto di questo capitolo coprirà i tipi incorporati di Protobuf e mostrerà come sono correlati ai tipi .NET comuni.</span><span class="sxs-lookup"><span data-stu-id="3f63a-131">The rest of this chapter will cover Protobuf's built-in types and show how they relate to common .NET types.</span></span>

> [!NOTE]
> <span data-ttu-id="3f63a-132">Protobuf non supporta in `decimal` modo nativo `double` un tipo, quindi viene usato.</span><span class="sxs-lookup"><span data-stu-id="3f63a-132">Protobuf doesn't natively support a `decimal` type, so `double` is used instead.</span></span> <span data-ttu-id="3f63a-133">Per le applicazioni che richiedono la precisione decimale completa, fare riferimento alla [sezione sui decimali](protobuf-data-types.md#decimals) nella parte successiva di questo capitolo.</span><span class="sxs-lookup"><span data-stu-id="3f63a-133">For applications that require full decimal precision, refer to the [section on decimals](protobuf-data-types.md#decimals) in the next part of this chapter.</span></span>

## <a name="the-generated-code"></a><span data-ttu-id="3f63a-134">Codice generato</span><span class="sxs-lookup"><span data-stu-id="3f63a-134">The generated code</span></span>

<span data-ttu-id="3f63a-135">Quando si compila l'applicazione, Protobuf crea classi per ognuno dei messaggi, eseguendo il mapping dei relativi tipi nativi ai tipi C.</span><span class="sxs-lookup"><span data-stu-id="3f63a-135">When you build your application, Protobuf creates classes for each of your messages, mapping its native types to C# types.</span></span> <span data-ttu-id="3f63a-136">Il `Stock` tipo generato avrà la firma seguente:The generated type would have the following signature:</span><span class="sxs-lookup"><span data-stu-id="3f63a-136">The generated `Stock` type would have the following signature:</span></span>

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

<span data-ttu-id="3f63a-137">Il codice effettivo generato è molto più complicato di questo.</span><span class="sxs-lookup"><span data-stu-id="3f63a-137">The actual code that's generated is far more complicated than this.</span></span> <span data-ttu-id="3f63a-138">Il motivo è che ogni classe contiene tutto il codice necessario per serializzare e deserializzare se stesso nel formato wire binario.</span><span class="sxs-lookup"><span data-stu-id="3f63a-138">The reason is that each class contains all the code necessary to serialize and deserialize itself to the binary wire format.</span></span>

### <a name="property-names"></a><span data-ttu-id="3f63a-139">Nomi delle proprietà</span><span class="sxs-lookup"><span data-stu-id="3f63a-139">Property names</span></span>

<span data-ttu-id="3f63a-140">Si noti che il `PascalCase` compilatore Protobuf `snake_case` applicato `.proto` ai nomi delle proprietà, anche se erano nel file.</span><span class="sxs-lookup"><span data-stu-id="3f63a-140">Note that the Protobuf compiler applied `PascalCase` to the property names, although they were `snake_case` in the `.proto` file.</span></span> <span data-ttu-id="3f63a-141">La guida di [stile Protobuf](https://developers.google.com/protocol-buffers/docs/style) consiglia di utilizzare `snake_case` nelle definizioni dei messaggi in modo che la generazione di codice per altre piattaforme produca il caso previsto per le convenzioni.</span><span class="sxs-lookup"><span data-stu-id="3f63a-141">The [Protobuf style guide](https://developers.google.com/protocol-buffers/docs/style) recommends using `snake_case` in your message definitions so that the code generation for other platforms produces the expected case for their conventions.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3f63a-142">[Successivo](protocol-buffers.md)
>[precedente](protobuf-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="3f63a-142">[Previous](protocol-buffers.md)
[Next](protobuf-data-types.md)</span></span>
