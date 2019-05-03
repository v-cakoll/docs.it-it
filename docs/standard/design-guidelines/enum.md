---
title: Progettazione di enum
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
author: KrzysztofCwalina
ms.openlocfilehash: c0645ba1179c4c6fd961b871b3061cd51174f427
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669095"
---
# <a name="enum-design"></a>Progettazione di enum
Le enumerazioni sono un tipo speciale di tipo di valore. Esistono due tipi di enumerazioni: semplice enumerazioni di flag e le enumerazioni.  
  
 Enumerazioni semplici rappresentano piccoli set chiuso di scelte. Un esempio comune di enumerazione semplice è un set di colori.  
  
 Enumerazioni di flag sono progettate per supportare le operazioni bit per bit sui valori di enumerazione. Un esempio comune di enumerazione flag è un elenco di opzioni.  
  
 **✓ DO** utilizzare un'enumerazione per tipizzare parametri, proprietà e restituiscono valori che rappresentano i set di valori.  
  
 **✓ DO** preferire l'utilizzo di un'enumerazione anziché costanti statiche.  
  
 **X DO NOT** utilizzare un tipo enum di set aperto (ad esempio la versione del sistema operativo, nomi degli amici, ecc.).  
  
 **X DO NOT** forniscono valori enum riservato che servono per utilizzi futuri.  
  
 È possibile aggiungere sempre semplicemente i valori per l'enumerazione esistente in una fase successiva. Visualizzare [aggiunta di valori per le enumerazioni](#add_value) per altri dettagli su come aggiungere i valori per le enumerazioni. Valori riservati solo contamina il set di valori reali e tendono a causare errori dell'utente.  
  
 **X AVOID** esporre pubblicamente le enumerazioni con un solo valore.  
  
 Una pratica comune per garantire l'estensibilità futura delle API C consiste nell'aggiungere parametri riservati per le firme del metodo. Tali parametri riservati possono essere espresse come le enumerazioni con un singolo valore predefinito. Non eseguire questa operazione per le API gestite. Metodi (overload) consente di aggiungere parametri nelle versioni future.  
  
 **X DO NOT** includono valori sentinel nelle enumerazioni.  
  
 Anche se in alcuni casi sono utili per gli sviluppatori di framework, i valori di sentinel sono confondere gli utenti del framework. Vengono utilizzati per tenere traccia dello stato di enum anziché da uno dei valori dal set rappresentato dal tipo enum.  
  
 **✓ DO** fornire un valore pari a zero sulle enumerazioni semplici.  
  
 Si consiglia di chiamare il valore simile a "None". Se tale valore non è appropriato per questa enumerazione specifica, il valore predefinito più comune per l'enumerazione deve essere assegnato il valore sottostante pari a zero.  
  
 **✓ CONSIDER** utilizzando <xref:System.Int32> (impostazione predefinita nella maggior parte dei linguaggi di programmazione) con il tipo sottostante di un'enumerazione, a meno che una delle seguenti è true:  
  
- L'enumerazione è un enum di flag e si dispone di più di 32 flag o si aspettano di avere più in futuro.  
  
- Il tipo sottostante deve essere diverso da quello <xref:System.Int32> per semplificare l'interoperabilità con codice non gestito è previsto delle enumerazioni di dimensioni diverse.  
  
- Un tipo sottostante di dimensioni minori comporta risparmi notevoli in uno spazio. Se si prevede che l'enumerazione da utilizzare principalmente come argomento per il flusso di controllo, le dimensioni poco rilevante. Il risparmio di dimensioni potrebbe essere significativo se:  
  
    - Si prevede che l'enumerazione da utilizzare come un campo in una struttura molto spesso un'istanza o una classe.  
  
    - Si prevede che agli utenti di creare matrici di grandi dimensioni o raccolte di istanze di enumerazione.  
  
    - Previsto un numero elevato di istanze dell'enumerazione da serializzare.  
  
 Per informazioni sull'utilizzo in memoria, tenere presente che gli oggetti gestiti siano sempre `DWORD`-allineati, pertanto è necessario in modo efficace più enumerazioni o altre strutture di piccole dimensioni in un'istanza per comprimere un'enumerazione con più piccola per fare la differenza, poiché la dimensione totale dell'istanza è sempre continua a essere arrotondato per eccesso una `DWORD`.  
  
 **✓ DO** denominare le enumerazioni di flag con plurale o sintagmi nominali e le enumerazioni semplici con singolare o sintagmi nominali.  
  
 **X DO NOT** estendere <xref:System.Enum?displayProperty=nameWithType> direttamente.  
  
 <xref:System.Enum?displayProperty=nameWithType> è un tipo speciale utilizzato da CLR per creare enumerazioni definite dall'utente. La maggior parte dei linguaggi di programmazione forniscono un elemento di programmazione che consente di accedere a questa funzionalità. Ad esempio, in c# il `enum` parola chiave viene usata per definire un'enumerazione.  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a>Progettazione enumerazioni di Flag  
 **✓ DO** applica il <xref:System.FlagsAttribute?displayProperty=nameWithType> per le enumerazioni di flag. Non si applica questo attributo per le enumerazioni semplici.  
  
 **✓ DO** utilizzano potenze di due per i valori di enumerazione flag pertanto possono essere liberamente combinati mediante un'operazione OR bit per bit.  
  
 **✓ CONSIDER** fornendo valori enum speciale per comunemente utilizzato le combinazioni di flag.  
  
 Operazioni bit per bit sono un concetto avanzato e non dovrebbero essere necessarie per eseguire semplici operazioni. <xref:System.IO.FileAccess.ReadWrite> è un esempio di un valore speciale.  
  
 **X AVOID** creazione le enumerazioni di flag in cui non sono valide alcune combinazioni di valori.  
  
 **X AVOID** utilizzando flag valori enum pari a zero, a meno che il valore rappresenta "tutti i flag vengono cancellati" ed è denominato in modo appropriato, come stabilito dalla linea guida successiva.  
  
 **✓ DO** denominare il valore zero di enumerazioni di flag `None`. Per un enum di flag, il valore deve sempre indicare che "tutti i flag vengono cancellati."  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a>Aggiunta di valore per le enumerazioni  
 È molto comune per individuare che è necessario aggiungere valori a un tipo enum dopo aver spedito già. È un potenziale problema di compatibilità dell'applicazione quando il valore appena aggiunto viene restituito da un'API esistente, poiché le applicazioni scritte in modo inadeguato non potrebbero gestire correttamente il nuovo valore.  
  
 **✓ CONSIDER** aggiunta di valori per le enumerazioni, nonostante un rischio per la compatibilità di piccole dimensioni.  
  
 Se si dispone di dati reali sull'incompatibilità delle applicazioni causati da aggiunte a un'enumerazione, è consigliabile aggiungere una nuova API che restituisce i valori vecchi e nuovi e deprecare l'API precedente, che deve continuare restituendo solo i valori precedenti. Ciò garantisce che le applicazioni esistenti restino compatibili.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di tipi](../../../docs/standard/design-guidelines/type.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
