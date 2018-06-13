---
title: Schema di configurazione di WCF
ms.date: 03/30/2017
ms.assetid: c282aeb5-91f0-4522-8e2f-704c1ef3651f
ms.openlocfilehash: bcbc12d35dae59fcd43d5fbf2d4c936c8e4a4423
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357028"
---
# <a name="wcf-configuration-schema"></a>Schema di configurazione di WCF
Gli elementi di configurazione di Windows Communication Foundation (WCF) consentono di configurare le applicazioni client e servizio WCF. È possibile usare lo [Strumento Editor di configurazione (SvcConfigEditor.exe)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) per creare e modificare i file di configurazione di client e servizi. Poiché i file di configurazione sono in formato XML, per modificarli manualmente usando un editor di testo è necessario avere familiarità con il linguaggio XML. In caso contrario, è possibile che si verifichino problemi. È ad esempio possibile che un tag di elemento XML o un attributo venga digitato in modo errato. Per i tag di elemento XML e gli attributi viene applicata la distinzione tra maiuscole e minuscole.  
  
 Il sistema di configurazione WCF si basa sul <xref:System.Configuration> dello spazio dei nomi. È pertanto possibile usare tutte le funzionalità standard fornite dallo spazio dei nomi <xref:System.Configuration>, ad esempio il blocco, la crittografia e l'unione delle impostazioni di configurazione, allo scopo di aumentare la sicurezza dell'applicazione e della relativa configurazione. Per altre informazioni su questi concetti, vedere gli argomenti seguenti.  
  
 [Crittografia delle informazioni di configurazione](http://go.microsoft.com/fwlink/?LinkId=95337)  
  
 [Blocco delle impostazioni di configurazione](http://go.microsoft.com/fwlink/?LinkId=95338)  
  
 Questa sezione descrive tutti i valori possibili di ogni elemento di configurazione e le relative interazioni con gli altri elementi di configurazione di WCF. Nella mappa seguente viene illustrato lo schema di configurazione di WCF.  
  
 ![Schema di configurazione di WCF](../../../../../docs/framework/configure-apps/file-schema/wcf/media/orcasconfigschema.gif "OrcasConfigSchema")  
  
> [!CAUTION]
>  È consigliabile proteggere i file di configurazione dell'applicazione (app. config) con accesso controllo Elenca (ACL) appropriato per impedire eventuali potenziali minacce per la sicurezza, tutte le sezioni di configurazione WCF.  Ad esempio, è necessario garantire che solo gli utenti appropriati siano in grado di accedere o apportare modifiche alla sezione del modello dei servizi del file di configurazione di un servizio o alle impostazioni di sicurezza relative alle associazioni dell'applicazione.  
  
## <a name="in-this-section"></a>In questa sezione  
 [\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
 Descrive l'elemento `ServiceModel`.  
  
 [\<system.serviceModel.activation>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)  
 Configura lo strumento SMSvcHost.exe.  
  
 [\<system.runtime.serialization>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
 Descrive l'elemento di livello superiore per l'impostazione delle opzioni quando si usano serializzatori quali <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Configurazione di applicazioni Windows Communication Foundation](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a)  
 Viene descritto come configurare i client e i servizi WCF.
