---
title: Considerazioni sulla sicurezza in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- security [XAML Services], .NET XAML services
- XAML security [XAML Services]
ms.assetid: 544296d4-f38e-4498-af49-c9f4dad28964
ms.openlocfilehash: 1864910b339c74e3033fb4d6d8baebffada1a4f8
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071689"
---
# <a name="xaml-security-considerations"></a>Considerazioni sulla sicurezza XAMLXAML security considerations

Questo articolo descrive le procedure consigliate per la sicurezza nelle applicazioni quando si usa l'API dei servizi XAML XAML e .NET.

## <a name="untrusted-xaml-in-applications"></a>XAML non attendibile nelle applicazioniUntrusted XAML in Applications

Nel senso più generale, XAML non attendibile è qualsiasi origine XAML che l'applicazione non include o genera in modo specifico.

XAML compilato o archiviato `resx`come risorsa di tipo all'interno di un assembly attendibile e firmato non è intrinsecamente non attendibile. È possibile considerare attendibile il codice XAML tanto quanto si considera attendibile l'assembly nel suo complesso. Nella maggior parte dei casi, si è interessati solo agli aspetti di attendibilità di XAML separato, ovvero un'origine XAML caricata da un flusso o da altri I/O. Loose XAML non è un componente specifico o una funzionalità di un modello di applicazione con un'infrastruttura di distribuzione e creazione di pacchetti. Tuttavia, un assembly potrebbe implementare un comportamento che comporta il caricamento di XAML separato.

Per XAML non attendibile, è consigliabile considerarlo in genere come se si trattasse di codice non attendibile. Usa il sandboxing o altre metafore per impedire a XAML potenzialmente non attendibile di accedere al codice attendibile.

La natura delle funzionalità XAML offre al codice XAML il diritto di costruire oggetti e impostarne le proprietà. Queste funzionalità includono anche l'accesso ai convertitori di tipi, il `x:Code` mapping e l'accesso agli assembly nel dominio applicazione, l'utilizzo di estensioni di markup, blocchi e così via.

Oltre alle funzionalità a livello di linguaggio, XAML viene usato per la definizione dell'interfaccia utente in molte tecnologie. Il caricamento di codice XAML non attendibile potrebbe comportare il caricamento di un'interfaccia utente di spoofing dannosa.

## <a name="sharing-context-between-readers-and-writers"></a>Condivisione del contesto tra lettori e scrittori

L'architettura dei servizi XAML .NET per i reader XAML e i writer XAML spesso richiede la condivisione di un reader XAML con un writer XAML o di un contesto dello schema XAML condiviso. La condivisione di oggetti o contesti potrebbe essere necessaria se si scrive la logica del ciclo del nodo XAML o si fornisce un percorso di salvataggio personalizzato. Non condividere istanze del lettore XAML, il contesto dello schema XAML non predefinito o le impostazioni per le classi reader/writer XAML tra codice attendibile e non attendibile.

La maggior parte degli scenari e delle operazioni che coinvolgono la scrittura di oggetti XAML per il supporto di un tipo basato su CLR possono usare solo il contesto dello schema XAML predefinito. Il contesto dello schema XAML predefinito non include in modo esplicito le impostazioni che potrebbero compromettere l'attendibilità totale. È quindi sicuro condividere il contesto tra componenti reader/writer XAML attendibili e non attendibili. Tuttavia, se si esegue questa operazione, è comunque consigliabile mantenere tali lettori e writer in ambiti separati, <xref:System.AppDomain> con uno di essi specificamente destinato/sandboxed per l'attendibilità parziale.

## <a name="xaml-namespaces-and-assembly-trust"></a>XAML Namespaces and Assembly Trust

La sintassi e la definizione di base non qualificate per il modo in cui XAML interpreta un mapping dello spazio dei nomi XAML personalizzato a un assembly non distingue tra un assembly attendibile e un assembly non attendibile caricato nel dominio applicazione. Pertanto, è tecnicamente possibile che un assembly non attendibile spoofi il mapping dello spazio dei nomi XAML previsto di un assembly attendibile e acquisisca le informazioni sull'oggetto e sulle proprietà dichiarate di un'origine XAML. Se si dispone di requisiti di sicurezza per evitare questa situazione, il mapping dello spazio dei nomi XAML previsto deve essere eseguito utilizzando una delle tecniche seguenti:If you have security requirements to avoid this situation, your intended XAML namespace mapping should be made using one of the following techniques:

- Usa un nome di assembly completo con nome sicuro in qualsiasi mapping dello spazio dei nomi XAML eseguito dal codice XAML dell'applicazione.

- Limitare il mapping degli assembly a un set <xref:System.Xaml.XamlSchemaContext> fisso di assembly di riferimento, creando un oggetto specifico per i reader XAML e i writer di oggetti XAML. Vedere <xref:System.Xaml.XamlSchemaContext.%23ctor%28System.Collections.Generic.IEnumerable%7BSystem.Reflection.Assembly%7D%29>.

## <a name="xaml-type-mapping-and-type-system-access"></a>Mapping dei tipi XAML e accesso al sistema di tipi

XAML supporta il proprio sistema di tipi, che in molti modi è un peer di come CLR implementa il sistema di tipi CLR di base. Tuttavia, per alcuni aspetti del riconoscimento dei tipi in cui si prendono decisioni di attendibilità su un tipo in base alle informazioni sul tipo, è necessario rinviare alle informazioni sul tipo nei tipi di supporto CLR. Ciò è dovuto al fatto che alcune delle funzionalità di creazione di report specifiche del sistema di tipi XAML vengono lasciate aperte come metodi virtuali e pertanto non sono completamente sotto il controllo delle implementazioni originali dei servizi XAML .NET. Questi punti di estendibilità esistono perché il sistema di tipi XAML è estensibile, in modo da corrispondere all'estensibilità di XAML stesso e alle possibili strategie alternative di mapping dei tipi rispetto all'implementazione supportata da CLR predefinita e al contesto dello schema XAML predefinito. Per ulteriori informazioni, vedere le note specifiche <xref:System.Xaml.XamlType> <xref:System.Xaml.XamlMember>su diverse proprietà di e .

## <a name="see-also"></a>Vedere anche

- <xref:System.Xaml.Permissions.XamlAccessLevel>
