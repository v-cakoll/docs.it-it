---
title: Considerazioni sulla sicurezza in XAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [XAML Services], .NET XAML services
- XAML security [XAML Services]
ms.assetid: 544296d4-f38e-4498-af49-c9f4dad28964
caps.latest.revision: "7"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b58719f36cd911497c5cd892610330688221e7ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="xaml-security-considerations"></a>Considerazioni sulla sicurezza in XAML
Questo argomento descrive le procedure consigliate per la protezione delle applicazioni quando si usa XAML e API dei servizi XAML di .NET Framework.  
  
## <a name="untrusted-xaml-in-applications"></a>XAML non attendibili nelle applicazioni  
 In senso più generale, XAML non attendibili è qualsiasi origine XAML che l'applicazione non specificamente includono o generare.  
  
 Il codice XAML viene compilato o archiviato come un `resx`-tipo di risorsa all'interno di un assembly attendibile e firmato non è considerato non attendibile. È possibile considerare attendibile il codice XAML in quanto si ritiene attendibile l'assembly nel suo complesso. Nella maggior parte dei casi, si teme solo con gli aspetti di attendibilità di XAML separato, ovvero un'origine XAML che è stato caricato da un flusso o un altro IO. XAML separato non è un componente specifico o una funzionalità di un modello di applicazione con una distribuzione e l'infrastruttura di creazione del pacchetto. Tuttavia, un assembly può implementare un comportamento che prevede il caricamento di XAML separato.  
  
 Per XAML non attendibili, devi considerarlo in genere lo stesso come se fosse codice non attendibile. Utilizzare il sandboxing o altre metafore per impedire l'accesso al codice attendibile XAML probabilmente non attendibile.  
  
 La natura della funzionalità di XAML fornisce il codice XAML il diritto di creare oggetti e impostare le relative proprietà. Queste funzionalità includono inoltre l'accesso a convertitori di tipi, mapping e l'accesso agli assembly nel dominio dell'applicazione, utilizzando le estensioni di markup, `x:Code` blocchi e così via.  
  
 Oltre alle relative funzionalità, a livello di linguaggio XAML viene utilizzato per la definizione dell'interfaccia utente in numerose tecnologie. Il caricamento di XAML non attendibili potrebbe comportare il caricamento di un'interfaccia utente di spoofing dannosa.  
  
## <a name="sharing-context-between-readers-and-writers"></a>Condivisione del contesto tra lettori e writer  
 L'architettura di servizi XAML di .NET Framework per i reader XAML e writer XAML spesso richiede che la condivisione di un reader XAML in un writer XAML, o un contesto dello schema XAML condiviso. La condivisione di oggetti o contesti potrebbe essere necessaria se si scrive logica di ciclo di nodi XAML o fornendo un oggetto personalizzato di percorso di salvataggio. Non è necessario condividere le istanze del reader XAML, il contesto dello schema XAML non predefinito o impostazioni per le classi di lettura/scrittura XAML tra codice attendibile e.  
  
 La maggior parte degli scenari e le operazioni di relative oggetto XAML scrittura per un tipo basato su CLR di supporto sufficiente utilizzare il contesto dello schema XAML predefinito. In modo esplicito il contesto dello schema XAML predefinito non include impostazioni che potrebbero compromettere l'attendibilità totale. In questo modo è possibile condividere contesto tra i componenti di lettura/scrittura attendibili e XAML. Tuttavia, se si esegue questa operazione, è comunque consigliabile mantenere tali reader e writer in separata <xref:System.AppDomain> ambiti, con uno di essi in modo specifico destinato/in modalità sandbox di attendibilità parziale.  
  
## <a name="xaml-namespaces-and-assembly-trust"></a>Spazi dei nomi XAML e attendibilità degli Assembly  
 La sintassi non qualificata di base e la definizione per l'interpretazione di XAML in un mapping dello spazio dei nomi XAML personalizzato a un assembly non viene fatta distinzione tra un assembly attendibile e come caricato nel dominio applicazione. Pertanto, è tecnicamente possibile per un assembly non attendibile effettuare lo spoofing di mapping dello spazio dei nomi XAML previsto dell'assembly attendibili e acquisire l'oggetto dichiarato di un'origine XAML e informazioni sulle proprietà. Se si dispone di requisiti di sicurezza per evitare questa situazione, previsto mapping dello spazio dei nomi XAML deve essere reso utilizzando una delle tecniche seguenti:  
  
-   Utilizzare un nome completo dell'assembly con nome sicuro il mapping dello spazio dei nomi XAML apportate da XAML dell'applicazione.  
  
-   Limitare il mapping a un set predefinito di assembly di riferimento, creando un oggetto specifico di assembly <xref:System.Xaml.XamlSchemaContext> per il codice XAML reader e XAML writer di oggetti. Vedere <xref:System.Xaml.XamlSchemaContext.%23ctor%28System.Collections.Generic.IEnumerable%7BSystem.Reflection.Assembly%7D%29>.  
  
## <a name="xaml-type-mapping-and-type-system-access"></a>Mapping di tipi XAML e tipo di accesso di sistema  
 XAML supporta il proprio sistema di tipo, che in molti modi è un peer di come CLR implementa il sistema di tipi CLR. Tuttavia, per alcuni aspetti di compatibilità dei tipi in cui si sono decisioni sull'attendibilità un tipo in base alle informazioni relative al tipo, è necessario fare riferimento le informazioni sui tipi in CLR a tipi di supporto. In questo modo alcune delle funzionalità di creazione di report specifiche del sistema di tipi XAML vengono lasciate aperte come metodi virtuali e di conseguenza, non sono completamente sotto il controllo delle implementazioni di servizi XAML di .NET Framework originale. Questi punti di estendibilità esistono perché il sistema di tipi XAML è estensibile, in modo che corrisponda l'estensibilità di XAML e relativo strategie di mapping dei tipi alternative possibili e l'implementazione CLR di backup predefinita e il contesto dello schema XAML predefinito. Per ulteriori informazioni, vedere le note specifiche per diverse proprietà di <xref:System.Xaml.XamlType> e <xref:System.Xaml.XamlMember>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Xaml.Permissions.XamlAccessLevel>
