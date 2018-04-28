---
title: Controllo di serializzazione e deserializzazione con SerializationBinder
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba8dcecf-acc7-467c-939d-021bbac797d4
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e41308de617fc02471ac2cb9769ec6e90e665e0b
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="controlling-serialization-and-deserialization-with-serializationbinder"></a><span data-ttu-id="9a72f-102">Controllo di serializzazione e deserializzazione con SerializationBinder</span><span class="sxs-lookup"><span data-stu-id="9a72f-102">Controlling Serialization and Deserialization with SerializationBinder</span></span>
<span data-ttu-id="9a72f-103">Durante la serializzazione un formattatore trasmette le informazioni necessarie per la creazione di un'istanza di un oggetto di tipo e versione corretti.</span><span class="sxs-lookup"><span data-stu-id="9a72f-103">During serialization, a formatter transmits the information required to create an instance of an object of the correct type and version.</span></span> <span data-ttu-id="9a72f-104">Tali informazioni comprendono in genere il nome completo del tipo e il nome dell'assembly dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="9a72f-104">This information generally includes the full type name and assembly name of the object.</span></span> <span data-ttu-id="9a72f-105">Per impostazione predefinita, la deserializzazione usa queste informazioni per creare un'istanza di un oggetto identico.</span><span class="sxs-lookup"><span data-stu-id="9a72f-105">By default, deserialization uses this information to create an instance of an identical object.</span></span> <span data-ttu-id="9a72f-106">Per alcuni utenti potrebbe essere necessario controllare la classe da serializzare e deserializzare, in quanto la classe originale potrebbe non esistere sul computer che esegue la deserializzazione o si è spostata tra gli assembly oppure su server e client sono necessarie versioni diverse della classe.</span><span class="sxs-lookup"><span data-stu-id="9a72f-106">Some users may need to control which class to serialize and deserialize, either because the original class may not exist on the machine performing deserialization, the original class has moved between assemblies, or a different version of the class is required on the server and client.</span></span> <span data-ttu-id="9a72f-107">Per altre informazioni, vedere [utilizzo di serializzazione dello strumento di associazione](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md).</span><span class="sxs-lookup"><span data-stu-id="9a72f-107">For more information, see [Usage of Serialization Binder](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="9a72f-108">Questa funzionalità è disponibile solo se si usa <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> o <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="9a72f-108">This functionality is only available when using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> or the <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span>  
  
## <a name="using-serializationbinder"></a><span data-ttu-id="9a72f-109">Uso di SerializationBinder</span><span class="sxs-lookup"><span data-stu-id="9a72f-109">Using SerializationBinder</span></span>  
 <span data-ttu-id="9a72f-110"><xref:System.Runtime.Serialization.SerializationBinder> è una classe astratta usata per controllare i tipi effettivi usati durante la serializzazione e la deserializzazione.</span><span class="sxs-lookup"><span data-stu-id="9a72f-110"><xref:System.Runtime.Serialization.SerializationBinder> is an abstract class used to control the actual types used during serialization and deserialization.</span></span> <span data-ttu-id="9a72f-111">Per controllare i tipi usati durante la serializzazione e la deserializzazione, derivare una classe da <xref:System.Runtime.Serialization.SerializationBinder> ed eseguire l'override dei metodi <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> e <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)>.</span><span class="sxs-lookup"><span data-stu-id="9a72f-111">To control the types used during serialization and deserialization, derive a class from <xref:System.Runtime.Serialization.SerializationBinder> and override the <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> and <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> methods.</span></span> <span data-ttu-id="9a72f-112">Il metodo <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> usa un elemento <xref:System.Type> e restituisce un nome tipo e assembly.</span><span class="sxs-lookup"><span data-stu-id="9a72f-112">The <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> method takes a <xref:System.Type> and returns an assembly and type name.</span></span> <span data-ttu-id="9a72f-113">Il metodo <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> usa un nome tipo e assembly e restituisce un elemento <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="9a72f-113">The <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> method takes an assembly and type name and returns a <xref:System.Type>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a72f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a72f-114">See Also</span></span>  
 [<span data-ttu-id="9a72f-115">Serializzazione e deserializzazione</span><span class="sxs-lookup"><span data-stu-id="9a72f-115">Serialization and Deserialization</span></span>](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)  
 [<span data-ttu-id="9a72f-116">Uso del gestore di associazione della serializzazione</span><span class="sxs-lookup"><span data-stu-id="9a72f-116">Usage of Serialization Binder</span></span>](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md)
