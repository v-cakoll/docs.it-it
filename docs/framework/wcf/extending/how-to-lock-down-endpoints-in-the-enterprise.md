---
title: "Procedura: bloccare gli endpoint nell'organizzazione"
ms.date: 03/30/2017
ms.assetid: 1b7eaab7-da60-4cf7-9d6a-ec02709cf75d
ms.openlocfilehash: 35b9a1dbebce48823799689a581033d0483c3984
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937672"
---
# <a name="how-to-lock-down-endpoints-in-the-enterprise"></a>Procedura: bloccare gli endpoint nell'organizzazione

Le aziende di grandi dimensioni spesso richiedono che le applicazioni vengano sviluppate in conformità con i criteri di sicurezza aziendali. Nell'argomento seguente viene illustrato come sviluppare e installare un validator dell'endpoint client che può essere utilizzato per convalidare tutte le applicazioni client Windows Communication Foundation (WCF) installate nei computer.

In questo caso, il validator è un validator client perché questo comportamento dell'endpoint viene aggiunto alla sezione client [\<commonBehaviors >](../../configure-apps/file-schema/wcf/commonbehaviors.md) nel file Machine. config. WCF carica i comportamenti degli endpoint comuni solo per le applicazioni client e carica i comportamenti del servizio comuni solo per le applicazioni di servizio. Per installare questo stesso validator per le applicazioni di servizio, il validator deve essere un comportamento del servizio. Per ulteriori informazioni, vedere la sezione [\<> CommonBehaviors](../../configure-apps/file-schema/wcf/commonbehaviors.md) .

> [!IMPORTANT]
> I comportamenti del servizio o dell'endpoint non contrassegnati con l'attributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) aggiunti alla sezione [\<commonBehaviors >](../../configure-apps/file-schema/wcf/commonbehaviors.md) di un file di configurazione non vengono eseguiti quando l'applicazione è in esecuzione in un ambiente parzialmente attendibile e non viene generata alcuna eccezione quando si verifica questa situazione. Per imporre l'esecuzione di comportamenti comuni, ad esempio validator, è necessario:
>
> - Contrassegnare il comportamento comune con l'attributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute> in modo che possa essere eseguito se distribuito come applicazione parzialmente attendibile. Si noti che è possibile impostare nel computer una voce di registro per impedire l'esecuzione degli assembly APTCA.
>
> - Assicurarsi che se l'applicazione viene distribuita come applicazione completamente attendibile che gli utenti non possono modificare le impostazioni di sicurezza per l'accesso al codice per eseguire l'applicazione in un ambiente parzialmente attendibile. In tal caso, il validator personalizzato non viene eseguito e non viene generata alcuna eccezione. Per verificare questo aspetto, vedere l'opzione `levelfinal` tramite [lo strumento criteri di sicurezza dall'accesso di codice (Caspol. exe)](../../tools/caspol-exe-code-access-security-policy-tool.md).
>
> Per ulteriori informazioni, vedere [procedure consigliate di attendibilità parziale](../feature-details/partial-trust-best-practices.md) e [scenari di distribuzione supportati](../feature-details/supported-deployment-scenarios.md).

### <a name="to-create-the-endpoint-validator"></a>Creazione del validator dell'endpoint.

1. Creare un oggetto <xref:System.ServiceModel.Description.IEndpointBehavior> con i passaggi di convalida desiderati nel metodo <xref:System.ServiceModel.Description.IEndpointBehavior.Validate%2A>. Nel codice seguente ne viene illustrato un esempio. Il `InternetClientValidatorBehavior` viene tratto dall'esempio di [convalida della sicurezza](../samples/security-validation.md) .

    [!code-csharp[LockdownValidation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorbehavior.cs#2)]

2. Creare un nuovo oggetto <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> che registra il validator dell'endpoint creato nel passaggio 1. Nell'esempio di codice seguente viene illustrata questa operazione. Il codice originale per questo esempio è nell'esempio di [convalida della sicurezza](../samples/security-validation.md) .

    [!code-csharp[LockdownValidation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorelement.cs#3)]

3. Verificare che l'assembly compilato sia firmato con un nome sicuro. Per informazioni dettagliate, vedere lo [strumento nome sicuro (sn. EXE)](../../tools/sn-exe-strong-name-tool.md) e i comandi del compilatore per il linguaggio in uso.

### <a name="to-install-the-validator-into-the-target-computer"></a>Installazione del validator nel computer di destinazione

1. Installare il validator dell'endpoint utilizzando il meccanismo appropriato. In un'azienda, è possibile usare a tale fine Criteri di gruppo e Systems Management Server (SMS).

2. Installare l'assembly con nome sicuro in Global Assembly Cache utilizzando [gacutil. exe (strumento Global assembly cache)](../../tools/gacutil-exe-gac-tool.md).

3. Usare i tipi di spazio dei nomi <xref:System.Configuration?displayProperty=nameWithType> per:

    1. Aggiungere l'estensione alla sezione [\<behaviorExtensions >](../../configure-apps/file-schema/wcf/behaviorextensions.md) utilizzando un nome di tipo completo e bloccare l'elemento.

         [!code-csharp[LockdownValidation#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#5)]

    2. Aggiungere l'elemento behavior alla proprietà `EndpointBehaviors` della sezione [\<commonBehaviors >](../../configure-apps/file-schema/wcf/commonbehaviors.md) e bloccare l'elemento. Per installare il validator nel servizio, il validator deve essere un <xref:System.ServiceModel.Description.IServiceBehavior> e aggiungerlo alla proprietà `ServiceBehaviors`. Nell'esempio di codice seguente viene illustrata la configurazione corretta dopo i passaggi a. e b., con la sola eccezione che non è presente un nome sicuro.

        [!code-csharp[LockdownValidation#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#6)]

    3. Salvare il file machine.config. Nell'esempio di codice seguente vengono eseguite tutte le attività nel passaggio 3, ma viene salvata localmente una copia del file machine.config modificato.

        [!code-csharp[LockdownValidation#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#7)]

## <a name="example"></a>Esempio

Nell'esempio di codice seguente viene illustrato come aggiungere un comportamento comune al file machine.config e salvare una copia sul disco. Il `InternetClientValidatorBehavior` viene tratto dall'esempio di [convalida della sicurezza](../samples/security-validation.md) .

[!code-csharp[LockdownValidation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#1)]

## <a name="net-framework-security"></a>Sicurezza di .NET Framework

Si potrebbe inoltre desiderare di crittografare gli elementi del file di configurazione. Per altre informazioni, vedere la sezione Vedere anche.

## <a name="see-also"></a>Vedere anche

- [Crittografia di elementi del file di configurazione tramite DPAPI](https://docs.microsoft.com/previous-versions/msp-n-p/ff647398(v=pandp.10))
- [Crittografia di elementi del file di configurazione tramite RSA](https://docs.microsoft.com/previous-versions/msp-n-p/ff650304(v=pandp.10))
