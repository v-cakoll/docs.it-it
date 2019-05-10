---
title: Considerazioni sulla sicurezza in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- security [XAML Services], .NET XAML services
- XAML security [XAML Services]
ms.assetid: 544296d4-f38e-4498-af49-c9f4dad28964
ms.openlocfilehash: 76dce711e46d267c85b0fc9426be452d90b4d07c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622836"
---
# <a name="xaml-security-considerations"></a>Considerazioni sulla sicurezza in XAML
In questo argomento descrive le procedure consigliate per la sicurezza in applicazioni quando si usa XAML e l'API di servizi XAML di .NET Framework.  
  
## <a name="untrusted-xaml-in-applications"></a>XAML non attendibili nelle applicazioni  
 In senso più generale, XAML non attendibili è qualsiasi origine XAML che l'applicazione è stata non specificamente includono o emit.  
  
 XAML che viene compilato o archiviato come un `resx`-tipo di risorsa all'interno di un assembly attendibile e firmato non è considerato non attendibile. È possibile considerare attendibile il XAML in quanto si ritiene attendibile l'assembly nel suo complesso. Nella maggior parte dei casi, si teme solo con gli aspetti di attendibilità di XAML separato, che rappresenta l'origine XAML viene caricato da un flusso o altri i/o. XAML Loose non è un componente specifico o una funzionalità di un modello di applicazione con un'infrastruttura di creazione di pacchetti e distribuzione. Tuttavia, un assembly può implementare un comportamento che prevede il caricamento di XAML loose.  
  
 Per XAML non attendibili, devi considerarlo in genere lo stesso come se fossero codice non attendibile. Usare il sandboxing o altri metafore per impedire l'accesso al codice attendibile di XAML potenzialmente non attendibili.  
  
 La natura delle funzionalità XAML offre il XAML il diritto di costruire oggetti e impostare le relative proprietà. Queste funzionalità includono anche l'accesso a convertitori di tipi, mapping e accesso agli assembly nel dominio dell'applicazione, usando le estensioni di markup, `x:Code` blocchi e così via.  
  
 Oltre alle funzionalità a livello di linguaggio, XAML viene utilizzato per la definizione dell'interfaccia utente in molte tecnologie. Il caricamento di XAML non attendibili può significare il caricamento di un'interfaccia utente di spoofing dannosa.  
  
## <a name="sharing-context-between-readers-and-writers"></a>Condivisione del contesto tra i lettori e writer  
 L'architettura di servizi XAML di .NET Framework per lettori XAML e writer XAML spesso richiede la condivisione di un lettore XAML per un writer XAML, o un contesto dello schema XAML condiviso. La condivisione di oggetti o contesti potrebbe essere necessaria se si sta scrivendo la logica di ciclo di nodi XAML o fornendo un oggetto personalizzato di percorso di salvataggio. Non si devono condividere le istanze del reader XAML, il contesto dello schema XAML non predefinito o le impostazioni per le classi di reader e writer XAML tra il codice attendibile e non attendibile.  
  
 La maggior parte degli scenari e le operazioni che interessano oggetto XAML scrittura per un tipo basato su Common Language Runtime supporta sufficiente utilizzare il contesto dello schema XAML predefinito. In modo esplicito il contesto dello schema XAML predefinito non include impostazioni che potrebbero compromettere l'attendibilità totale. In questo modo è possibile condividere contesto tra attendibili e componenti di reader e writer XAML. Tuttavia, se in questo caso, è comunque consigliabile tenere separati questi lettori e writer <xref:System.AppDomain> ambiti, con uno di essi in particolare previsto/sandbox per un'attendibilità parziale.  
  
## <a name="xaml-namespaces-and-assembly-trust"></a>Spazi dei nomi XAML e attendibilità degli Assembly  
 La sintassi non qualificata di base e una definizione per il modo in cui XAML interpreta un mapping dello spazio dei nomi XAML personalizzato a un assembly non viene fatta distinzione tra un assembly attendibile e come caricati nel dominio dell'applicazione. Di conseguenza, è tecnicamente possibile per un assembly non attendibile effettuare lo spoofing il mapping dello spazio dei nomi XAML desiderato dell'assembly attendibili e acquisire informazioni sulle proprietà e oggetto dichiarato di un'origine XAML. Se si dispone di requisiti di sicurezza per evitare questa situazione, il mapping dello spazio dei nomi XAML previsto deve essere effettuato utilizzando una delle tecniche seguenti:  
  
- Usare un nome completo dell'assembly con nome sicuro in qualsiasi mapping dello spazio dei nomi XAML effettuate da XAML dell'applicazione.  
  
- Limitare il mapping a un set fisso di assembly di riferimento, costruendo un oggetto specifico di assembly <xref:System.Xaml.XamlSchemaContext> per il XAML reader e XAML writer di oggetti. Vedere <xref:System.Xaml.XamlSchemaContext.%23ctor%28System.Collections.Generic.IEnumerable%7BSystem.Reflection.Assembly%7D%29>.  
  
## <a name="xaml-type-mapping-and-type-system-access"></a>Mapping dei tipi XAML e l'accesso di sistema di tipo  
 XAML supporta un proprio sistema di tipi, che in molti modi è un peer a come CLR implementa il sistema di tipi CLR. Tuttavia, per alcuni aspetti di consapevolezza di tipo in cui si apportano le decisioni sull'attendibilità relative a un tipo basato su informazioni relative al tipo, è necessario fare riferimento le informazioni sui tipi in CLR i tipi di supporto. Infatti, alcune delle funzionalità di creazione di report specifiche del sistema di tipi XAML vengono lasciate aperte come metodi virtuali e di conseguenza, non sono completamente sotto il controllo delle implementazioni dei servizi XAML di .NET Framework originale. Questi punti di estendibilità esistono perché il sistema di tipi XAML è estensibile, in base l'estensibilità di XAML stesso e le strategie di mapping dei tipi alternative possibili e l'implementazione predefinita supportata da Common Language Runtime e il contesto dello schema XAML predefinito. Per altre informazioni, vedere le note specifiche su alcune delle proprietà del <xref:System.Xaml.XamlType> e <xref:System.Xaml.XamlMember>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xaml.Permissions.XamlAccessLevel>
