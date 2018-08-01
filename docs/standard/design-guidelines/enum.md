---
title: Progettazione di enum
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 544f617ca3a352814504125d7a61d70db5a81566
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33579249"
---
# <a name="enum-design"></a>Progettazione di enum
Le enumerazioni sono un tipo speciale di tipo di valore. Esistono due tipi di enumerazioni: enumerazioni semplici di enumerazioni e flag.  
  
 Le enumerazioni semplici rappresentano piccoli set chiuso di scelte. Un esempio comune di enum semplice è un set di colori.  
  
 Enumerazioni di flag sono progettate per supportare le operazioni bit per bit sui valori enum. Un esempio comune di enumerazione di flag è un elenco di opzioni.  
  
 **✓ DO** utilizzare un'enumerazione per tipizzare parametri, proprietà e restituiscono valori che rappresentano i set di valori.  
  
 **✓ DO** preferire l'utilizzo di un'enumerazione anziché costanti statiche.  
  
 **X DO NOT** utilizzare un tipo enum di set aperto (ad esempio la versione del sistema operativo, nomi degli amici, ecc.).  
  
 **X DO NOT** forniscono valori enum riservato che servono per utilizzi futuri.  
  
 È possibile aggiungere sempre semplicemente i valori per l'enumerazione esistente in una fase successiva. Vedere [aggiunta di valori per le enumerazioni](#add_value) per ulteriori informazioni sull'aggiunta di valori per le enumerazioni. Valori riservati è sufficiente eseguire il set di valori reali e tendono a causare errori dell'utente.  
  
 **X AVOID** esporre pubblicamente le enumerazioni con un solo valore.  
  
 Una pratica comune per garantire l'estendibilità futura delle API C consiste nell'aggiungere parametri riservati per le firme del metodo. Tali parametri riservati possono essere espresso come le enumerazioni con un valore singolo predefinito. Questo non deve essere eseguito nel API gestite. L'overload di metodo consente di aggiungere parametri nelle versioni future.  
  
 **X DO NOT** includono valori sentinel nelle enumerazioni.  
  
 Anche se sono a volte utile agli sviluppatori framework, valori sentinel possono generare confusione per gli utenti di framework. Vengono utilizzati per tenere traccia dello stato della fase uno dei valori enum piuttosto che dal set di rappresentato dal tipo enum.  
  
 **✓ DO** fornire un valore pari a zero sulle enumerazioni semplici.  
  
 Si consiglia di chiamare il valore simile al seguente "None". Se tale valore non è appropriato per questa enumerazione specifica, più comune assegnato il valore predefinito per l'enumerazione deve essere il valore sottostante pari a zero.  
  
 **✓ CONSIDER** utilizzando <xref:System.Int32> (impostazione predefinita nella maggior parte dei linguaggi di programmazione) con il tipo sottostante di un'enumerazione, a meno che una delle seguenti è true:  
  
-   Il valore enum è un flag e disporre di più di 32 flag oppure prevede che più in futuro.  
  
-   Il tipo sottostante deve essere diverso da quello <xref:System.Int32> per semplificare l'interoperabilità con codice non gestito, che prevede le enumerazioni di dimensioni diverse.  
  
-   Un tipo più piccolo sottostante comporta un notevole risparmio di spazio. Se si prevede che l'enumerazione venga utilizzata principalmente come argomento per il flusso di controllo, le dimensioni poco rilevante. Il risparmio di dimensioni potrebbe essere significativo se:  
  
    -   Si prevede che l'enumerazione da utilizzare come campo in una struttura con una frequenza elevata di un'istanza o una classe.  
  
    -   Si prevede che agli utenti di creare matrici di grandi dimensioni o le raccolte delle istanze dell'enum.  
  
    -   Si prevede un numero elevato di istanze di enum deve essere serializzato.  
  
 Per informazioni sull'utilizzo in memoria, tenere presente che gli oggetti gestiti sono sempre `DWORD`-allineato, pertanto è necessario in modo efficace più enumerazioni o altre strutture di piccole dimensioni in un'istanza per comprimere un enum con più piccoli per creare una differenza, perché la dimensione totale di istanza è sempre continua a essere arrotondato per eccesso un `DWORD`.  
  
 **✓ DO** denominare le enumerazioni di flag con plurale o sintagmi nominali e le enumerazioni semplici con singolare o sintagmi nominali.  
  
 **X DO NOT** estendere <xref:System.Enum?displayProperty=nameWithType> direttamente.  
  
 <xref:System.Enum?displayProperty=nameWithType> un tipo speciale utilizzato da CLR per creare enumerazioni definite dall'utente. La maggior parte dei linguaggi di programmazione fornisce un elemento di programmazione che consente di accedere a questa funzionalità. Ad esempio, in c# il `enum` parola chiave viene utilizzata per definire un'enumerazione.  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a>Enumerazioni di Flag progettazione  
 **✓ DO** applica il <xref:System.FlagsAttribute?displayProperty=nameWithType> per le enumerazioni di flag. Non si applica questo attributo per le enumerazioni semplici.  
  
 **✓ DO** utilizzano potenze di due per i valori di enumerazione flag pertanto possono essere liberamente combinati mediante un'operazione OR bit per bit.  
  
 **✓ CONSIDER** fornendo valori enum speciale per comunemente utilizzato le combinazioni di flag.  
  
 Operazioni bit per bit sono un concetto avanzato e non devono essere richiesta per eseguire semplici operazioni. <xref:System.IO.FileAccess.ReadWrite> è un esempio di un valore speciale.  
  
 **X AVOID** creazione le enumerazioni di flag in cui non sono valide alcune combinazioni di valori.  
  
 **X AVOID** utilizzando flag valori enum pari a zero, a meno che il valore rappresenta "tutti i flag vengono cancellati" ed è denominato in modo appropriato, come stabilito dalla linea guida successiva.  
  
 **✓ DO** denominare il valore zero di enumerazioni di flag `None`. Per un'enumerazione di flag, il valore deve sempre indicare che "tutti i flag sono cancellati."  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a>Aggiunta di valore alle enumerazioni  
 È molto comune per rilevare che è necessario aggiungere valori a un'enumerazione dopo che già spediti. È un potenziale problema di compatibilità dell'applicazione quando il valore appena aggiunto viene restituito da un'API esistente, poiché le applicazioni scritte in modo inadeguato non potrebbero gestire correttamente il nuovo valore.  
  
 **✓ CONSIDER** aggiunta di valori per le enumerazioni, nonostante un rischio per la compatibilità di piccole dimensioni.  
  
 Se si dispone di dati reali relativi incompatibilità causati da aggiunte a un'enumerazione, è possibile aggiungere una nuova API che restituisce i valori vecchi e nuovi e deprecare l'API precedente, che deve continuare la restituzione solo i valori precedenti. Ciò garantisce che le applicazioni esistenti sono compatibili.  
  
 *Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche  
 [Linee guida per la progettazione di tipi](../../../docs/standard/design-guidelines/type.md)  
 [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
