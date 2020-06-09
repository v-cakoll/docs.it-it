---
title: ConfigurationCodeGenerator
ms.date: 03/30/2017
ms.assetid: 3913aae8-165f-4014-9262-7fe426f90cb2
ms.openlocfilehash: d64be95f71f840e08ede63e1c1f14ee08e52ce97
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592476"
---
# <a name="configurationcodegenerator"></a>ConfigurationCodeGenerator
ConfigurationCodeGenerator è un strumento che consente di esporre le implementazioni del canale personalizzate nel sistema di configurazione. In questo modo gli utenti del canale personalizzato possono configurare il canale utilizzando un file con estensione config nello stesso modo in cui configurerebbero un'associazione fornita dal sistema, ad esempio `NetTcpBinding`, o un'associazione personalizzata utilizzando `TcpTransportBindingElement`.  
  
 Quando si scrive un canale personalizzato e lo si espone al modello di programmazione utilizzando un elemento `BindingElement` o `Binding` nuovo, è necessario creare un set di classi per rendere `BindingElement` o `Binding` configurabile utilizzando un file config. È possibile utilizzare lo strumento ConfigurationCodeGenerator per generare queste classi e migliorare l'esperienza del cliente.  
  
### <a name="to-build-the-tool"></a>Per compilare lo strumento  
  
1. Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).  
  
2. La compilazione della soluzione genera il file ConfigurationCodeGenerator.exe. Il file SampleRun. cmd include una riga di comando di esempio che illustra come usare questo strumento per generare le classi per l'esempio [Transport: UDP](transport-udp.md) .  
  
### <a name="to-run-the-tool"></a>Per eseguire lo strumento  
  
1. Al prompt dei comandi digitare quanto segue se si dispone di un tipo `BindingElement` personalizzato e un tipo `Binding` personalizzato:  
  
    ```console  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereTheseTypesAreDefined  
    ```  
  
     In alternativa, digitare quanto segue se si dispone solo di un tipo `BindingElement` personalizzato:  
  
    ```console  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /dll: TheAssemblyWhereThisTypeIsDefined  
    ```  
  
     In alternativa, digitare quanto segue se si dispone solo di un tipo `Binding` personalizzato:  
  
    ```console  
    ConfigurationCodeGenerator.exe /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereThisTypeIsDefined  
    ```  
  
     Il comando genera tre file con estensione cs per `BindingElement` (se si specifica l'opzione /be:), cinque file cs per l'elemento `Binding` standard (se si specifica l'opzione /sb:) e un file xml.  
  
    1. Se si utilizza l'opzione /be, uno dei file cs implementa `BindingElementExtensionSection` per l'elemento di associazione. Questo codice espone `BindingElement` al sistema di configurazione, in modo che le altre associazioni personalizzate possono utilizzare l'elemento di associazione. Gli altri file dispongono di classi che rappresentano impostazioni predefinite e costanti. Nei file sono presenti i commenti `//TODO` per ricordare l'aggiornamento dei valori predefiniti.  
  
    2. Se si specifica il l'opzione /sb, due dei file cs implementano rispettivamente un `StandardBindingElement` e un `StandardBindingCollectionElement` che espongono l'associazione standard al sistema di configurazione. Gli altri file dispongono di classi che rappresentano impostazioni predefinite e costanti. Nei file sono presenti i commenti `//TODO` per ricordare l'aggiornamento dei valori predefiniti.  
  
         Se è stata specificata l'opzione l'/SB: CodeToAddTo \<*YourStdBinding*> . cs contiene codice che è necessario aggiungere manualmente alla classe che implementa l'associazione standard.  
  
     Il file SampleConfig.xml contiene il codice di configurazione che è necessario aggiungere al file di configurazione che registra i gestori definiti nel passaggio 1 o 2 precedente.  
