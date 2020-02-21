---
title: Messaggi di protobuf-gRPC per sviluppatori WCF
description: Informazioni sul modo in cui i messaggi protobuf vengono definiti in IDL C#e generati in.
ms.date: 09/09/2019
ms.openlocfilehash: c7375bafb7572b0eaa0458b0310a0114e3fd078c
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543040"
---
# <a name="protobuf-messages"></a><span data-ttu-id="0c26e-103">Messaggi protobuf</span><span class="sxs-lookup"><span data-stu-id="0c26e-103">Protobuf messages</span></span>

<span data-ttu-id="0c26e-104">In questa sezione viene illustrato come dichiarare messaggi del buffer del protocollo (protobuf) nei file di `.proto`.</span><span class="sxs-lookup"><span data-stu-id="0c26e-104">This section covers how to declare Protocol Buffer (Protobuf) messages in `.proto` files.</span></span> <span data-ttu-id="0c26e-105">Vengono illustrati i concetti fondamentali relativi ai numeri e ai tipi di campo e viene C# esaminato il codice generato dal compilatore `protoc`.</span><span class="sxs-lookup"><span data-stu-id="0c26e-105">It explains the fundamental concepts of field numbers and types, and it looks at the C# code that the `protoc` compiler generates.</span></span> 

<span data-ttu-id="0c26e-106">Nella parte restante del capitolo verranno esaminati in modo più dettagliato il modo in cui i diversi tipi di dati sono rappresentati in protobuf.</span><span class="sxs-lookup"><span data-stu-id="0c26e-106">The rest of the chapter will look in more detail at how different types of data are represented in Protobuf.</span></span>

## <a name="declaring-a-message"></a><span data-ttu-id="0c26e-107">Dichiarazione di un messaggio</span><span class="sxs-lookup"><span data-stu-id="0c26e-107">Declaring a message</span></span>

<span data-ttu-id="0c26e-108">In Windows Communication Foundation (WCF), una classe `Stock` per un'applicazione commerciale del mercato azionario potrebbe essere definita come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0c26e-108">In Windows Communication Foundation (WCF), a `Stock` class for a stock market trading application might be defined like the following example:</span></span>

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

<span data-ttu-id="0c26e-109">Per implementare la classe equivalente in protobuf, è necessario dichiararla nel file di `.proto`.</span><span class="sxs-lookup"><span data-stu-id="0c26e-109">To implement the equivalent class in Protobuf, you must declare it in the `.proto` file.</span></span> <span data-ttu-id="0c26e-110">Il compilatore `protoc` genererà la classe .NET come parte del processo di compilazione.</span><span class="sxs-lookup"><span data-stu-id="0c26e-110">The `protoc` compiler will then generate the .NET class as part of the build process.</span></span>

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

<span data-ttu-id="0c26e-111">Nella prima riga viene dichiarata la versione della sintassi utilizzata.</span><span class="sxs-lookup"><span data-stu-id="0c26e-111">The first line declares the syntax version being used.</span></span> <span data-ttu-id="0c26e-112">La versione 3 della lingua è stata rilasciata nel 2016.</span><span class="sxs-lookup"><span data-stu-id="0c26e-112">Version 3 of the language was released in 2016.</span></span> <span data-ttu-id="0c26e-113">Si tratta della versione consigliata per i servizi gRPC.</span><span class="sxs-lookup"><span data-stu-id="0c26e-113">It's the version that we recommend for gRPC services.</span></span>

<span data-ttu-id="0c26e-114">La riga di `option csharp_namespace` specifica lo spazio dei nomi da utilizzare per C# i tipi generati.</span><span class="sxs-lookup"><span data-stu-id="0c26e-114">The `option csharp_namespace` line specifies the namespace to be used for the generated C# types.</span></span> <span data-ttu-id="0c26e-115">Questa opzione verrà ignorata quando il file di `.proto` viene compilato per altre lingue.</span><span class="sxs-lookup"><span data-stu-id="0c26e-115">This option will be ignored when the `.proto` file is compiled for other languages.</span></span> <span data-ttu-id="0c26e-116">I file protobuf spesso contengono opzioni specifiche della lingua per diverse lingue.</span><span class="sxs-lookup"><span data-stu-id="0c26e-116">Protobuf files often contain language-specific options for several languages.</span></span>

<span data-ttu-id="0c26e-117">Nella definizione del messaggio `Stock` sono specificati quattro campi.</span><span class="sxs-lookup"><span data-stu-id="0c26e-117">The `Stock` message definition specifies four fields.</span></span> <span data-ttu-id="0c26e-118">Ogni ha un tipo, un nome e un numero di campo.</span><span class="sxs-lookup"><span data-stu-id="0c26e-118">Each has a type, a name, and a field number.</span></span>

## <a name="field-numbers"></a><span data-ttu-id="0c26e-119">Numeri di campo</span><span class="sxs-lookup"><span data-stu-id="0c26e-119">Field numbers</span></span>

<span data-ttu-id="0c26e-120">I numeri di campo sono una parte importante di protobuf.</span><span class="sxs-lookup"><span data-stu-id="0c26e-120">Field numbers are an important part of Protobuf.</span></span> <span data-ttu-id="0c26e-121">Vengono usati per identificare i campi nei dati con codifica binaria, che significa che non possono essere modificati dalla versione alla versione del servizio.</span><span class="sxs-lookup"><span data-stu-id="0c26e-121">They're used to identify fields in the binary encoded data, which means they can't change from version to version of your service.</span></span> <span data-ttu-id="0c26e-122">Il vantaggio è che sono possibili compatibilità con le versioni precedenti e compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="0c26e-122">The advantage is that backward compatibility and forward compatibility are possible.</span></span> <span data-ttu-id="0c26e-123">I client e i servizi ignoreranno semplicemente i numeri di campo che non conoscono, purché venga gestita la possibilità di valori mancanti.</span><span class="sxs-lookup"><span data-stu-id="0c26e-123">Clients and services will simply ignore field numbers that they don't know about, as long as the possibility of missing values is handled.</span></span>

<span data-ttu-id="0c26e-124">Nel formato binario, il numero di campo viene combinato con un identificatore di tipo.</span><span class="sxs-lookup"><span data-stu-id="0c26e-124">In the binary format, the field number is combined with a type identifier.</span></span> <span data-ttu-id="0c26e-125">I numeri di campo da 1 a 15 possono essere codificati con il relativo tipo come singolo byte.</span><span class="sxs-lookup"><span data-stu-id="0c26e-125">Field numbers from 1 to 15 can be encoded with their type as a single byte.</span></span> <span data-ttu-id="0c26e-126">I numeri da 16 a 2.047 accettano 2 byte.</span><span class="sxs-lookup"><span data-stu-id="0c26e-126">Numbers from 16 to 2,047 take 2 bytes.</span></span> <span data-ttu-id="0c26e-127">Se sono necessari più di 2.047 campi in un messaggio per qualsiasi motivo, è possibile passare a un livello superiore.</span><span class="sxs-lookup"><span data-stu-id="0c26e-127">You can go higher if you need more than 2,047 fields on a message for any reason.</span></span> <span data-ttu-id="0c26e-128">Gli identificatori a byte singolo per i numeri di campo da 1 a 15 offrono prestazioni migliori, quindi è consigliabile usarli per i campi più semplici e usati di frequente.</span><span class="sxs-lookup"><span data-stu-id="0c26e-128">The single byte identifiers for field numbers 1 to 15 offer better performance, so you should use them for the most basic, frequently used fields.</span></span>

## <a name="types"></a><span data-ttu-id="0c26e-129">Tipi</span><span class="sxs-lookup"><span data-stu-id="0c26e-129">Types</span></span>

<span data-ttu-id="0c26e-130">Le dichiarazioni di tipo utilizzano i tipi di dati scalari nativi di protobuf, che vengono discussi in modo più dettagliato nella [sezione successiva](protobuf-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="0c26e-130">The type declarations are using Protobuf's native scalar data types, which are discussed in more detail in [the next section](protobuf-data-types.md).</span></span> <span data-ttu-id="0c26e-131">Nella parte restante di questo capitolo vengono illustrati i tipi incorporati di protobuf e viene illustrato il modo in cui sono correlati ai tipi .NET comuni.</span><span class="sxs-lookup"><span data-stu-id="0c26e-131">The rest of this chapter will cover Protobuf's built-in types and show how they relate to common .NET types.</span></span>

> [!NOTE]
> <span data-ttu-id="0c26e-132">Protobuf non supporta in modo nativo un tipo di `decimal`, quindi viene invece utilizzato `double`.</span><span class="sxs-lookup"><span data-stu-id="0c26e-132">Protobuf doesn't natively support a `decimal` type, so `double` is used instead.</span></span> <span data-ttu-id="0c26e-133">Per le applicazioni che richiedono una precisione decimale completa, fare riferimento alla [sezione relativa ai numeri decimali](protobuf-data-types.md#decimals) nella parte successiva di questo capitolo.</span><span class="sxs-lookup"><span data-stu-id="0c26e-133">For applications that require full decimal precision, refer to the [section on decimals](protobuf-data-types.md#decimals) in the next part of this chapter.</span></span>

## <a name="the-generated-code"></a><span data-ttu-id="0c26e-134">Codice generato</span><span class="sxs-lookup"><span data-stu-id="0c26e-134">The generated code</span></span>

<span data-ttu-id="0c26e-135">Quando si compila l'applicazione, protobuf crea le classi per ogni messaggio, eseguendo il mapping dei tipi nativi C# ai tipi.</span><span class="sxs-lookup"><span data-stu-id="0c26e-135">When you build your application, Protobuf creates classes for each of your messages, mapping its native types to C# types.</span></span> <span data-ttu-id="0c26e-136">Il tipo di `Stock` generato avrà la firma seguente:</span><span class="sxs-lookup"><span data-stu-id="0c26e-136">The generated `Stock` type would have the following signature:</span></span>

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

<span data-ttu-id="0c26e-137">Il codice effettivo generato è molto più complicato di questo.</span><span class="sxs-lookup"><span data-stu-id="0c26e-137">The actual code that's generated is far more complicated than this.</span></span> <span data-ttu-id="0c26e-138">Il motivo è che ogni classe contiene tutto il codice necessario per la serializzazione e la deserializzazione nel formato wire binario.</span><span class="sxs-lookup"><span data-stu-id="0c26e-138">The reason is that each class contains all the code necessary to serialize and deserialize itself to the binary wire format.</span></span>

### <a name="property-names"></a><span data-ttu-id="0c26e-139">Nomi delle proprietà</span><span class="sxs-lookup"><span data-stu-id="0c26e-139">Property names</span></span>

<span data-ttu-id="0c26e-140">Si noti che il compilatore protobuf applicato `PascalCase` ai nomi delle proprietà, anche se sono stati `snake_case` nel file `.proto`.</span><span class="sxs-lookup"><span data-stu-id="0c26e-140">Note that the Protobuf compiler applied `PascalCase` to the property names, although they were `snake_case` in the `.proto` file.</span></span> <span data-ttu-id="0c26e-141">La [Guida di stile protobuf](https://developers.google.com/protocol-buffers/docs/style) consiglia di usare `snake_case` nelle definizioni dei messaggi in modo che la generazione di codice per altre piattaforme produca il caso previsto per le convenzioni.</span><span class="sxs-lookup"><span data-stu-id="0c26e-141">The [Protobuf style guide](https://developers.google.com/protocol-buffers/docs/style) recommends using `snake_case` in your message definitions so that the code generation for other platforms produces the expected case for their conventions.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0c26e-142">[Precedente](protocol-buffers.md)
>[Successivo](protobuf-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="0c26e-142">[Previous](protocol-buffers.md)
[Next](protobuf-data-types.md)</span></span>
