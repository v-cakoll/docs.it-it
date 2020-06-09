---
title: Tipi conosciuti di contratto dati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], known types
- KnownTypeAttribute [WCF]
- KnownTypes [WCF]
ms.assetid: 1a0baea1-27b7-470d-9136-5bbad86c4337
ms.openlocfilehash: b7d78def4d656dea59af5400c7ed7deeef28cd0c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597449"
---
# <a name="data-contract-known-types"></a><span data-ttu-id="723ca-102">Tipi conosciuti di contratto dati</span><span class="sxs-lookup"><span data-stu-id="723ca-102">Data Contract Known Types</span></span>
<span data-ttu-id="723ca-103">La classe <xref:System.Runtime.Serialization.KnownTypeAttribute> consente di specificare, in anticipo, i tipi che devono essere presi in considerazione durante la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="723ca-103">The <xref:System.Runtime.Serialization.KnownTypeAttribute> class allows you to specify, in advance, the types that should be included for consideration during deserialization.</span></span> <span data-ttu-id="723ca-104">Per un esempio pratico, vedere l'esempio [Known Types](../samples/known-types.md) .</span><span class="sxs-lookup"><span data-stu-id="723ca-104">For a working example, see the [Known Types](../samples/known-types.md) example.</span></span>  
  
 <span data-ttu-id="723ca-105">In genere, quando si passano parametri e valori restituiti tra un client e un servizio, entrambi gli endpoint condividono tutti i contratti dati dei dati da trasmettere.</span><span class="sxs-lookup"><span data-stu-id="723ca-105">Normally, when passing parameters and return values between a client and a service, both endpoints share all of the data contracts of the data to be transmitted.</span></span> <span data-ttu-id="723ca-106">Nelle circostanze seguenti, tuttavia, la situazione è diversa:</span><span class="sxs-lookup"><span data-stu-id="723ca-106">However, this is not the case in the following circumstances:</span></span>  
  
- <span data-ttu-id="723ca-107">Il contratto dati inviato deriva dal contratto dati previsto.</span><span class="sxs-lookup"><span data-stu-id="723ca-107">The sent data contract is derived from the expected data contract.</span></span> <span data-ttu-id="723ca-108">Per ulteriori informazioni, vedere la sezione relativa all'ereditarietà nell' [equivalenza dei contratti dati](data-contract-equivalence.md).</span><span class="sxs-lookup"><span data-stu-id="723ca-108">For more information, see the section about inheritance in [Data Contract Equivalence](data-contract-equivalence.md)).</span></span> <span data-ttu-id="723ca-109">In tale caso, i dati trasmessi non hanno lo stesso contratto dati previsto dall'endpoint di destinazione.</span><span class="sxs-lookup"><span data-stu-id="723ca-109">In that case, the transmitted data does not have the same data contract as expected by the receiving endpoint.</span></span>  
  
- <span data-ttu-id="723ca-110">Il tipo dichiarato per le informazioni da trasmettere è un'interfaccia, anziché una classe, una struttura o un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="723ca-110">The declared type for the information to be transmitted is an interface, as opposed to a class, structure, or enumeration.</span></span> <span data-ttu-id="723ca-111">Non è pertanto possibile conoscere in anticipo quale tipo che implementa l'interfaccia viene effettivamente inviato e, di conseguenza, l'endpoint di destinazione non è in grado di determinare, in anticipo, il contratto dati per i dati trasmessi.</span><span class="sxs-lookup"><span data-stu-id="723ca-111">Therefore, it cannot be known in advance which type that implements the interface is actually sent and therefore, the receiving endpoint cannot determine in advance the data contract for the transmitted data.</span></span>  
  
- <span data-ttu-id="723ca-112">Il tipo dichiarato per le informazioni da trasmettere è <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="723ca-112">The declared type for the information to be transmitted is <xref:System.Object>.</span></span> <span data-ttu-id="723ca-113">Dato che ogni tipo eredita da <xref:System.Object>e che non è possibile sapere in anticipo qual è il tipo effettivamente inviato, l'endpoint di destinazione non è in grado di determinare in anticipo il contratto dati per i dati trasmessi.</span><span class="sxs-lookup"><span data-stu-id="723ca-113">Because every type inherits from <xref:System.Object>, and it cannot be known in advance which type is actually sent, the receiving endpoint cannot determine in advance the data contract for the transmitted data.</span></span> <span data-ttu-id="723ca-114">Questo è un caso speciale del primo elemento: ogni contratto dati deriva dall'impostazione predefinita, un contratto dati vuoto generato per <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="723ca-114">This is a special case of the first item: Every data contract derives from the default, a blank data contract that is generated for <xref:System.Object>.</span></span>  
  
- <span data-ttu-id="723ca-115">Alcuni tipi, che includono .NET Framework tipi, hanno membri che si trovano in una delle tre categorie precedenti.</span><span class="sxs-lookup"><span data-stu-id="723ca-115">Some types, which include .NET Framework types, have members that are in one of the preceding three categories.</span></span> <span data-ttu-id="723ca-116"><xref:System.Collections.Hashtable> , ad esempio, utilizza <xref:System.Object> per memorizzare gli oggetti effettivi nella tabella hash.</span><span class="sxs-lookup"><span data-stu-id="723ca-116">For example, <xref:System.Collections.Hashtable> uses <xref:System.Object> to store the actual objects in the hash table.</span></span> <span data-ttu-id="723ca-117">Durante la serializzazione di questi tipi, il lato di destinazione non è in grado di determinare in anticipo il contratto dati per questi membri.</span><span class="sxs-lookup"><span data-stu-id="723ca-117">When serializing these types, the receiving side cannot determine in advance the data contract for these members.</span></span>  
  
## <a name="the-knowntypeattribute-class"></a><span data-ttu-id="723ca-118">Classe KnownTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="723ca-118">The KnownTypeAttribute Class</span></span>  
 <span data-ttu-id="723ca-119">Quando i dati arrivano a un endpoint di destinazione, il runtime WCF tenta di deserializzare i dati in un'istanza di un tipo Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="723ca-119">When data arrives at a receiving endpoint, the WCF runtime attempts to deserialize the data into an instance of a common language runtime (CLR) type.</span></span> <span data-ttu-id="723ca-120">Il tipo di cui viene creata l'istanza per la deserializzazione viene scelto controllando innanzitutto il messaggio in arrivo per determinare il contratto dati al quale è compatibile con il contenuto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="723ca-120">The type that is instantiated for deserialization is chosen by first inspecting the incoming message to determine the data contract to which the contents of the message conform.</span></span> <span data-ttu-id="723ca-121">Il motore di deserializzazione tenta quindi di trovare un tipo CLR che implementi un contratto dati conforme al contenuto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="723ca-121">The deserialization engine then attempts to find a CLR type that implements a data contract compatible with the message contents.</span></span> <span data-ttu-id="723ca-122">Il set di tipi di candidato consentiti dal motore di deserializzazione durante questo processo viene chiamato set di "tipi noti" del deserializzatore.</span><span class="sxs-lookup"><span data-stu-id="723ca-122">The set of candidate types that the deserialization engine allows for during this process is referred to as the deserializer's set of "known types."</span></span>  
  
 <span data-ttu-id="723ca-123">Un modo per consentire al motore di deserializzazione di conoscere un tipo consiste nell'utilizzare <xref:System.Runtime.Serialization.KnownTypeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="723ca-123">One way to let the deserialization engine know about a type is by using the <xref:System.Runtime.Serialization.KnownTypeAttribute>.</span></span> <span data-ttu-id="723ca-124">L'attributo non può essere applicato a membri dati singoli, ma solo a tutti i tipi di contratto dati.</span><span class="sxs-lookup"><span data-stu-id="723ca-124">The attribute cannot be applied to individual data members, only to whole data contract types.</span></span> <span data-ttu-id="723ca-125">L'attributo viene applicato a un *tipo esterno* che può essere una classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="723ca-125">The attribute is applied to an *outer type* that can be a class or a structure.</span></span> <span data-ttu-id="723ca-126">Nell'utilizzo più elementare, l'applicazione dell'attributo specifica un tipo come "tipo conosciuto".</span><span class="sxs-lookup"><span data-stu-id="723ca-126">In its most basic usage, applying the attribute specifies a type as a "known type."</span></span> <span data-ttu-id="723ca-127">Ciò fa sì che il tipo conosciuto sia parte di questo set di tipi noti ogni volta che viene deserializzato un oggetto del tipo esterno o un qualsiasi oggetto a cui si faccia riferimento tramite i suoi membri.</span><span class="sxs-lookup"><span data-stu-id="723ca-127">This causes the known type to be a part of the set of known types whenever an object of the outer type or any object referred to through its members is being deserialized.</span></span> <span data-ttu-id="723ca-128">Allo stesso tipo è possibile applicare più di un attributo <xref:System.Runtime.Serialization.KnownTypeAttribute> .</span><span class="sxs-lookup"><span data-stu-id="723ca-128">More than one <xref:System.Runtime.Serialization.KnownTypeAttribute> attribute can be applied to the same type.</span></span>  
  
## <a name="known-types-and-primitives"></a><span data-ttu-id="723ca-129">Tipi conosciuti e primitivi</span><span class="sxs-lookup"><span data-stu-id="723ca-129">Known Types and Primitives</span></span>  
 <span data-ttu-id="723ca-130">I tipi primitivi, così come certi tipi trattati come primitivi (ad esempio, <xref:System.DateTime> e <xref:System.Xml.XmlElement>) sono sempre "conosciuti" e non è mai necessario aggiungerli tramite questo meccanismo.</span><span class="sxs-lookup"><span data-stu-id="723ca-130">Primitive types, as well as certain types treated as primitives (for example, <xref:System.DateTime> and <xref:System.Xml.XmlElement>) are always "known" and never have to be added through this mechanism.</span></span> <span data-ttu-id="723ca-131">Le matrici di tipi primitivi, tuttavia, devono essere aggiunte in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="723ca-131">However, arrays of primitive types have to be added explicitly.</span></span> <span data-ttu-id="723ca-132">La maggior parte delle raccolte è considerata equivalente alle matrici.</span><span class="sxs-lookup"><span data-stu-id="723ca-132">Most collections are considered equivalent to arrays.</span></span> <span data-ttu-id="723ca-133">(La raccolte non generiche sono considerate equivalenti alle matrici di <xref:System.Object>).</span><span class="sxs-lookup"><span data-stu-id="723ca-133">(Non-generic collections are considered equivalent to arrays of <xref:System.Object>).</span></span> <span data-ttu-id="723ca-134">Per un esempio di utilizzo di primitivi, matrici di primitivi e raccolte di primitivi, vedere l'esempio 4.</span><span class="sxs-lookup"><span data-stu-id="723ca-134">For an example of the using primitives, primitive arrays, and primitive collections, see Example 4.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="723ca-135">A differenza di altri tipi di primitivi, la struttura <xref:System.DateTimeOffset> non è un tipo conosciuto per impostazione predefinita, pertanto deve essere aggiunta manualmente all'elenco dei tipi noti.</span><span class="sxs-lookup"><span data-stu-id="723ca-135">Unlike other primitive types, the <xref:System.DateTimeOffset> structure is not a known type by default, so it must be manually added to the list of known types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="723ca-136">Esempi</span><span class="sxs-lookup"><span data-stu-id="723ca-136">Examples</span></span>  
 <span data-ttu-id="723ca-137">Negli esempi seguenti viene illustrata la classe <xref:System.Runtime.Serialization.KnownTypeAttribute> utilizzata.</span><span class="sxs-lookup"><span data-stu-id="723ca-137">The following examples show the <xref:System.Runtime.Serialization.KnownTypeAttribute> class in use.</span></span>  
  
#### <a name="example-1"></a><span data-ttu-id="723ca-138">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="723ca-138">Example 1</span></span>  
 <span data-ttu-id="723ca-139">Esistono tre classi con una relazione di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="723ca-139">There are three classes with an inheritance relationship.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#1)]
 [!code-vb[C_KnownTypeAttribute#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#1)]  
  
 <span data-ttu-id="723ca-140">La classe `CompanyLogo` seguente può essere serializzata, ma non può essere deserializzata se il membro `ShapeOfLogo` è impostato su un `CircleType` o su un oggetto `TriangleType` , perché il motore di deserializzazione non riconosce alcun tipo con i nomi del contratto dati "Circle" o "Triangle".</span><span class="sxs-lookup"><span data-stu-id="723ca-140">The following `CompanyLogo` class can be serialized, but cannot be deserialized if the `ShapeOfLogo` member is set to either a `CircleType` or a `TriangleType` object, because the deserialization engine does not recognize any types with data contract names "Circle" or "Triangle."</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#2)]
 [!code-vb[C_KnownTypeAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#2)]  
  
 <span data-ttu-id="723ca-141">La modalità corretta per scrivere il tipo `CompanyLogo` è illustrata nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="723ca-141">The correct way to write the `CompanyLogo` type is shown in the following code.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#3)]
 [!code-vb[C_KnownTypeAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#3)]  
  
 <span data-ttu-id="723ca-142">Ogni volta che il tipo esterno `CompanyLogo2` viene deserializzato, il motore di deserializzazione viene a conoscenza di `CircleType` e `TriangleType` e, pertanto, è in grado di cercare i tipi corrispondenti per i contratti dati "Circle" e "Triangle".</span><span class="sxs-lookup"><span data-stu-id="723ca-142">Whenever the outer type `CompanyLogo2` is being deserialized, the deserialization engine knows about `CircleType` and `TriangleType` and, therefore, is able to find matching types for the "Circle" and "Triangle" data contracts.</span></span>  
  
#### <a name="example-2"></a><span data-ttu-id="723ca-143">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="723ca-143">Example 2</span></span>  
 <span data-ttu-id="723ca-144">Nell'esempio seguente, anche se sia `CustomerTypeA` che `CustomerTypeB` hanno il contratto dati `Customer` , viene creata un'istanza di `CustomerTypeB` ogni volta che viene deserializzato un `PurchaseOrder` , perché solo `CustomerTypeB` è conosciuto al motore di deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="723ca-144">In the following example, even though both `CustomerTypeA` and `CustomerTypeB` have the `Customer` data contract, an instance of `CustomerTypeB` is created whenever a `PurchaseOrder` is deserialized, because only `CustomerTypeB` is known to the deserialization engine.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#4)]
 [!code-vb[C_KnownTypeAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#4)]  
  
#### <a name="example-3"></a><span data-ttu-id="723ca-145">Esempio 3:</span><span class="sxs-lookup"><span data-stu-id="723ca-145">Example 3</span></span>  
 <span data-ttu-id="723ca-146">Nell'esempio seguente, un <xref:System.Collections.Hashtable> memorizza internamente il contenuto come <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="723ca-146">In the following example, a <xref:System.Collections.Hashtable> stores its contents internally as <xref:System.Object>.</span></span> <span data-ttu-id="723ca-147">Per deserializzare correttamente una tabella hash, il motore di deserializzazione deve conoscere il set dei tipi possibili che possono verificarsi.</span><span class="sxs-lookup"><span data-stu-id="723ca-147">To successfully deserialize a hash table, the deserialization engine must know the set of possible types that can occur there.</span></span> <span data-ttu-id="723ca-148">In questo caso, si sa in anticipo che solo gli oggetti `Book` e `Magazine` vengono memorizzati in `Catalog`, pertanto vengono aggiunti utilizzando l'attributo <xref:System.Runtime.Serialization.KnownTypeAttribute> .</span><span class="sxs-lookup"><span data-stu-id="723ca-148">In this case, we know in advance that only `Book` and `Magazine` objects are stored in the `Catalog`, so those are added using the <xref:System.Runtime.Serialization.KnownTypeAttribute> attribute.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#5)]
 [!code-vb[C_KnownTypeAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#5)]  
  
#### <a name="example-4"></a><span data-ttu-id="723ca-149">Esempio 4</span><span class="sxs-lookup"><span data-stu-id="723ca-149">Example 4</span></span>  
 <span data-ttu-id="723ca-150">Nell'esempio seguente, un contratto dati memorizza un numero e un'operazione da eseguire sul numero.</span><span class="sxs-lookup"><span data-stu-id="723ca-150">In the following example, a data contract stores a number and an operation to perform on the number.</span></span> <span data-ttu-id="723ca-151">Il membro dati `Numbers` può essere un numero Integer, una matrice di numeri Integer o un oggetto <xref:System.Collections.Generic.List%601> che contiene numeri Integer.</span><span class="sxs-lookup"><span data-stu-id="723ca-151">The `Numbers` data member can be an integer, an array of integers, or a <xref:System.Collections.Generic.List%601> that contains integers.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="723ca-152">Questo funzionerà sul lato client solo se SVCUTIL.EXE è utilizzato per generare un proxy WCF.</span><span class="sxs-lookup"><span data-stu-id="723ca-152">This will only work on the client side if SVCUTIL.EXE is used to generate a WCF proxy.</span></span> <span data-ttu-id="723ca-153">SVCUTIL.EXE recupera metadati dal servizio inclusi tutti i tipi noti.</span><span class="sxs-lookup"><span data-stu-id="723ca-153">SVCUTIL.EXE retrieves metadata from the service including any known types.</span></span> <span data-ttu-id="723ca-154">Senza queste informazioni un client non sarà in grado di deserializzare i tipi.</span><span class="sxs-lookup"><span data-stu-id="723ca-154">Without this information a client will not be able to deserialize the types.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#6)]
 [!code-vb[C_KnownTypeAttribute#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#6)]  
  
 <span data-ttu-id="723ca-155">Questo è il codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="723ca-155">This is the application code.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#7)]
 [!code-vb[C_KnownTypeAttribute#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#7)]  
  
## <a name="known-types-inheritance-and-interfaces"></a><span data-ttu-id="723ca-156">Tipi conosciuti, ereditarietà e interfacce</span><span class="sxs-lookup"><span data-stu-id="723ca-156">Known Types, Inheritance, and Interfaces</span></span>  
 <span data-ttu-id="723ca-157">Quando un tipo conosciuto è associato a un particolare tipo utilizzando l'attributo `KnownTypeAttribute` , il tipo conosciuto viene associato anche a tutti i tipi derivati di quel tipo.</span><span class="sxs-lookup"><span data-stu-id="723ca-157">When a known type is associated with a particular type using the `KnownTypeAttribute` attribute, the known type is also associated with all of the derived types of that type.</span></span> <span data-ttu-id="723ca-158">Si consideri, ad esempio, il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="723ca-158">For example, see the following code.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#8)]
 [!code-vb[C_KnownTypeAttribute#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#8)]  
  
 <span data-ttu-id="723ca-159">La classe `DoubleDrawing` non richiede l'attributo `KnownTypeAttribute` per utilizzare `Square` e `Circle` nel campo `AdditionalShape` , perché nella classe di base (`Drawing`) questi attributi sono già applicati.</span><span class="sxs-lookup"><span data-stu-id="723ca-159">The `DoubleDrawing` class does not require the `KnownTypeAttribute` attribute to use `Square` and `Circle` in the `AdditionalShape` field, because the base class (`Drawing`) already has these attributes applied.</span></span>  
  
 <span data-ttu-id="723ca-160">I tipi noti possono essere associati solo a classi e strutture, non a interfacce.</span><span class="sxs-lookup"><span data-stu-id="723ca-160">Known types can be associated only with classes and structures, not interfaces.</span></span>  
  
## <a name="known-types-using-open-generic-methods"></a><span data-ttu-id="723ca-161">Tipi conosciuti che utilizzano metodi generici aperti</span><span class="sxs-lookup"><span data-stu-id="723ca-161">Known Types Using Open Generic Methods</span></span>  
 <span data-ttu-id="723ca-162">Potrebbe essere necessario aggiungere un tipo generico come tipo conosciuto.</span><span class="sxs-lookup"><span data-stu-id="723ca-162">It may be necessary to add a generic type as a known type.</span></span> <span data-ttu-id="723ca-163">Non è tuttavia possibile passare un tipo generico aperto come parametro all'attributo `KnownTypeAttribute` .</span><span class="sxs-lookup"><span data-stu-id="723ca-163">However, an open generic type cannot be passed as a parameter to the `KnownTypeAttribute` attribute.</span></span>  
  
 <span data-ttu-id="723ca-164">Questo problema può essere risolto utilizzando un meccanismo alternativo, ovvero scrivere un metodo che restituisca un elenco di tipi da aggiungere alla raccolta di tipi noti.</span><span class="sxs-lookup"><span data-stu-id="723ca-164">This problem can be solved by using an alternative mechanism: Write a method that returns a list of types to add to the known types collection.</span></span> <span data-ttu-id="723ca-165">Specificare quindi il nome del metodo come argomento di tipo stringa per l'attributo `KnownTypeAttribute` , per far fronte ad alcune restrizioni.</span><span class="sxs-lookup"><span data-stu-id="723ca-165">The name of the method is then specified as a string argument to the `KnownTypeAttribute` attribute due to some restrictions.</span></span>  
  
 <span data-ttu-id="723ca-166">Il metodo deve esistere nel tipo al quale è applicato l'attributo `KnownTypeAttribute` , deve essere statico, non deve accettare parametri e deve restituire un oggetto che possa essere assegnato a <xref:System.Collections.IEnumerable> di <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="723ca-166">The method must exist on the type to which the `KnownTypeAttribute` attribute is applied, must be static, must accept no parameters, and must return an object that can be assigned to <xref:System.Collections.IEnumerable> of <xref:System.Type>.</span></span>  
  
 <span data-ttu-id="723ca-167">Non è possibile combinare l'attributo `KnownTypeAttribute` con un nome di metodo e attributi `KnownTypeAttribute` con i tipi effettivi sullo stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="723ca-167">You cannot combine the `KnownTypeAttribute` attribute with a method name and `KnownTypeAttribute` attributes with actual types on the same type.</span></span> <span data-ttu-id="723ca-168">Non è inoltre possibile applicare più di un `KnownTypeAttribute` con un nome di metodo allo stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="723ca-168">Furthermore, you cannot apply more than one `KnownTypeAttribute` with a method name to the same type.</span></span>  
  
 <span data-ttu-id="723ca-169">Fare riferimento alla classe seguente.</span><span class="sxs-lookup"><span data-stu-id="723ca-169">See the following class.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#9)]
 [!code-vb[C_KnownTypeAttribute#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#9)]  
  
 <span data-ttu-id="723ca-170">Il campo `theDrawing` contiene istanze di una classe `ColorDrawing` generica e una classe `BlackAndWhiteDrawing`generica, che ereditano entrambe da una classe `Drawing`generica.</span><span class="sxs-lookup"><span data-stu-id="723ca-170">The `theDrawing` field contains instances of a generic class `ColorDrawing` and a generic class `BlackAndWhiteDrawing`, both of which inherit from a generic class `Drawing`.</span></span> <span data-ttu-id="723ca-171">In genere, è necessario aggiungerle entrambe a tipi noti, ma quella che segue non è una sintassi valida per gli attributi.</span><span class="sxs-lookup"><span data-stu-id="723ca-171">Normally, both must be added to known types, but the following is not valid syntax for attributes.</span></span>  
  
```csharp  
// Invalid syntax for attributes:  
// [KnownType(typeof(ColorDrawing<T>))]  
// [KnownType(typeof(BlackAndWhiteDrawing<T>))]  
```  
  
```vb  
' Invalid syntax for attributes:  
' <KnownType(GetType(ColorDrawing(Of T))), _  
' KnownType(GetType(BlackAndWhiteDrawing(Of T)))>  
```  
  
 <span data-ttu-id="723ca-172">Per restituire questi tipi, è pertanto necessario creare un metodo.</span><span class="sxs-lookup"><span data-stu-id="723ca-172">Thus, a method must be created to return these types.</span></span> <span data-ttu-id="723ca-173">Nel codice seguente viene illustrato il modo corretto per scrivere questo tipo.</span><span class="sxs-lookup"><span data-stu-id="723ca-173">The correct way to write this type, then, is shown in the following code.</span></span>  
  
 [!code-csharp[C_KnownTypeAttribute#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_knowntypeattribute/cs/source.cs#10)]
 [!code-vb[C_KnownTypeAttribute#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_knowntypeattribute/vb/source.vb#10)]  
  
## <a name="additional-ways-to-add-known-types"></a><span data-ttu-id="723ca-174">Altri modi per aggiungere tipi noti.</span><span class="sxs-lookup"><span data-stu-id="723ca-174">Additional Ways to Add Known Types</span></span>  
 <span data-ttu-id="723ca-175">I tipi noti possono essere aggiunti anche tramite un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="723ca-175">Additionally, known types can be added through a configuration file.</span></span> <span data-ttu-id="723ca-176">Questa opzione è utile quando non si controlla il tipo che richiede tipi noti per la deserializzazione corretta, ad esempio quando si utilizzano librerie dei tipi di terze parti con Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="723ca-176">This is useful when you do not control the type that requires known types for proper deserialization, such as when using third-party type libraries with Windows Communication Foundation (WCF).</span></span>  
  
 <span data-ttu-id="723ca-177">Nel file di configurazione seguente viene illustrato come specificare un tipo conosciuto in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="723ca-177">The following configuration file shows how to specify a known type in a configuration file.</span></span>  
  
 `<configuration>`  
  
 `<system.runtime.serialization>`  
  
 `<dataContractSerializer>`  
  
 `<declaredTypes>`  
  
 `<add type="MyCompany.Library.Shape,`  
  
 `MyAssembly, Version=2.0.0.0, Culture=neutral,`  
  
 `PublicKeyToken=XXXXXX, processorArchitecture=MSIL">`  
  
 `<knownType type="MyCompany.Library.Circle,`  
  
 `MyAssembly, Version=2.0.0.0, Culture=neutral,`  
  
 `PublicKeyToken=XXXXXX, processorArchitecture=MSIL"/>`  
  
 `</add>`  
  
 `</declaredTypes>`  
  
 `</dataContractSerializer>`  
  
 `</system.runtime.serialization>`  
  
 `</configuration>`  
  
 <span data-ttu-id="723ca-178">Nel file di configurazione precedente è stato dichiarato che un tipo di contratto dati chiamato `MyCompany.Library.Shape` ha `MyCompany.Library.Circle` come tipo conosciuto.</span><span class="sxs-lookup"><span data-stu-id="723ca-178">In the preceding configuration file a data contract type called `MyCompany.Library.Shape` is declared to have `MyCompany.Library.Circle` as a known type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="723ca-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="723ca-179">See also</span></span>

- <xref:System.Runtime.Serialization.KnownTypeAttribute>
- <xref:System.Collections.Hashtable>
- <xref:System.Object>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.DataContractSerializer.KnownTypes%2A>
- [<span data-ttu-id="723ca-180">Tipi conosciuti</span><span class="sxs-lookup"><span data-stu-id="723ca-180">Known Types</span></span>](../samples/known-types.md)
- [<span data-ttu-id="723ca-181">Data Contract Equivalence</span><span class="sxs-lookup"><span data-stu-id="723ca-181">Data Contract Equivalence</span></span>](data-contract-equivalence.md)
- [<span data-ttu-id="723ca-182">Progettazione dei contratti di servizio</span><span class="sxs-lookup"><span data-stu-id="723ca-182">Designing Service Contracts</span></span>](../designing-service-contracts.md)
