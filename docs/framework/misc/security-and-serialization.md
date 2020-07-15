---
title: Sicurezza e serializzazione
description: Scopri di più su sicurezza e serializzazione. Utilizzare SecurityPermission con il flag SerializationFormatter specificato per visualizzare o modificare i dati dell'istanza dell'oggetto.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- code security, serialization
- serialization, security
- secure coding, serialization
- security [.NET Framework], serialization
ms.assetid: b921bc94-bd3a-4c91-9ede-2c8d4f78ea9a
ms.openlocfilehash: f19641ad2154631b4eab5104252c12b73b9084fd
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309274"
---
# <a name="security-and-serialization"></a><span data-ttu-id="4953f-104">Sicurezza e serializzazione</span><span class="sxs-lookup"><span data-stu-id="4953f-104">Security and serialization</span></span>

<span data-ttu-id="4953f-105">Poiché la serializzazione può consentire a un altro codice di visualizzare o modificare i dati dell'istanza di un oggetto che sarebbero altrimenti inaccessibili, è necessaria una speciale autorizzazione per il codice che esegue la serializzazione: <xref:System.Security.Permissions.SecurityPermission> con il flag <xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter> specificato.</span><span class="sxs-lookup"><span data-stu-id="4953f-105">Because serialization can allow other code to see or modify object instance data that would otherwise be inaccessible, a special permission is required of code performing serialization: <xref:System.Security.Permissions.SecurityPermission> with the <xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter> flag specified.</span></span> <span data-ttu-id="4953f-106">In base ai criteri predefiniti, questa autorizzazione non è concessa a codice scaricato da Internet o a codice Intranet, ma solo al codice presente sul computer locale.</span><span class="sxs-lookup"><span data-stu-id="4953f-106">Under default policy, this permission is not given to Internet-downloaded or intranet code; only code on the local computer is granted this permission.</span></span>  
  
 <span data-ttu-id="4953f-107">In genere, tutti i campi dell'istanza di un oggetto vengono serializzati e quindi i dati vengono rappresentati nei dati serializzati per l'istanza.</span><span class="sxs-lookup"><span data-stu-id="4953f-107">Normally, all fields of an object instance are serialized, meaning that data is represented in the serialized data for the instance.</span></span> <span data-ttu-id="4953f-108">Per un codice in grado di interpretare il formato è possibile determinare quali siano i valori dei dati, indipendentemente dall'accessibilità del membro.</span><span class="sxs-lookup"><span data-stu-id="4953f-108">It is possible for code that can interpret the format to determine what the data values are, independent of the accessibility of the member.</span></span> <span data-ttu-id="4953f-109">Analogamente, la deserializzazione estrae i dati dalla rappresentazione serializzata e imposta direttamente lo stato dell'oggetto, sempre indipendentemente dalle regole di accessibilità.</span><span class="sxs-lookup"><span data-stu-id="4953f-109">Similarly, deserialization extracts data from the serialized representation and sets object state directly, again irrespective of accessibility rules.</span></span>  
  
 <span data-ttu-id="4953f-110">È consigliabile rendere non serializzabili gli oggetti che possono contenere dati sensibili alla sicurezza, se possibile.</span><span class="sxs-lookup"><span data-stu-id="4953f-110">Any object that could contain security-sensitive data should be made nonserializable, if possible.</span></span> <span data-ttu-id="4953f-111">Se devono essere serializzabili, è opportuno creare campi specifici per i dati sensibili non serializzabili.</span><span class="sxs-lookup"><span data-stu-id="4953f-111">If it must be serializable, try to make specific fields that hold sensitive data nonserializable.</span></span> <span data-ttu-id="4953f-112">Se questi campi non possono essere resi non serializzabili, i dati sensibili verranno esposti a qualsiasi codice che disponga dell'autorizzazione per la serializzazione.</span><span class="sxs-lookup"><span data-stu-id="4953f-112">If those fields cannot be made nonserializable, the sensitive data will be exposed to any code that has permission to serialize.</span></span> <span data-ttu-id="4953f-113">Assicurarsi che nessun codice dannoso possa ottenere questa autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="4953f-113">Make sure that no malicious code can get this permission.</span></span>  
  
 <span data-ttu-id="4953f-114">L'interfaccia <xref:System.Runtime.Serialization.ISerializable> può essere usata solo dall'infrastruttura di serializzazione,</span><span class="sxs-lookup"><span data-stu-id="4953f-114">The <xref:System.Runtime.Serialization.ISerializable> interface is intended for use only by the serialization infrastructure.</span></span> <span data-ttu-id="4953f-115">ma, se non viene protetta, potrebbe diffondere informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="4953f-115">However, if unprotected, it can potentially release sensitive information.</span></span> <span data-ttu-id="4953f-116">Se si fornisce la serializzazione personalizzata implementando **ISerializable**, assicurarsi di prendere le precauzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4953f-116">If you provide custom serialization by implementing **ISerializable**, make sure you take the following precautions:</span></span>  
  
- <span data-ttu-id="4953f-117">Il metodo <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> deve essere protetto in modo esplicito richiedendo **SecurityPermission** con l'autorizzazione **SerializationFormatter** specificata o assicurandosi che nessuna informazione riservata venga rilasciata con l'output del metodo.</span><span class="sxs-lookup"><span data-stu-id="4953f-117">The <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> method should be explicitly secured either by demanding the **SecurityPermission** with **SerializationFormatter** permission specified or by making sure that no sensitive information is released with the method output.</span></span> <span data-ttu-id="4953f-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4953f-118">For example:</span></span>  
  
    ```vb  
    Public Overrides<SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter := True)>  _  
    Sub GetObjectData(info As SerializationInfo, context As StreamingContext)  
    End Sub  
    ```  
  
    ```csharp  
    [SecurityPermissionAttribute(SecurityAction.Demand,SerializationFormatter
    =true)]  
    public override void GetObjectData(SerializationInfo info,
    StreamingContext context)  
    {  
    }  
    ```  
  
- <span data-ttu-id="4953f-119">Lo speciale costruttore usato per la serializzazione deve anche eseguire la convalida di input approfondita ed essere protetto o privato per salvaguardarsi dal rischio di un uso improprio da parte del malware.</span><span class="sxs-lookup"><span data-stu-id="4953f-119">The special constructor used for serialization should also perform thorough input validation and should be either protected or private to help protect against misuse by malicious code.</span></span> <span data-ttu-id="4953f-120">È consigliabile che applichi gli stessi controlli e autorizzazioni di sicurezza necessari per ottenere un'istanza di tale classe in qualsiasi altro modo, ad esempio creando la classe esplicitamente oppure indirettamente con alcuni tipi di factory.</span><span class="sxs-lookup"><span data-stu-id="4953f-120">It should enforce the same security checks and permissions required to obtain an instance of such a class by any other means, such as explicitly creating the class or indirectly creating it through some kind of factory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4953f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4953f-121">See also</span></span>

- [<span data-ttu-id="4953f-122">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="4953f-122">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
