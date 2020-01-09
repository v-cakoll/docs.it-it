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
ms.openlocfilehash: 130e9b4e7f8d7076d1dc3f21f51dc07a68799bbe
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709452"
---
# <a name="enum-design"></a>Progettazione di enum

Le enumerazioni sono un tipo speciale di tipo di valore. Esistono due tipi di enumerazioni: enum semplici ed enumerazioni di flag.

Le enumerazioni semplici rappresentano set di scelte chiusi di piccole dimensioni. Un esempio comune di enum semplice è costituito da un set di colori.

Le enumerazioni di flag sono progettate per supportare operazioni bit per bit sui valori enum. Un esempio comune di enumerazione Flags è un elenco di opzioni.

**✓ DO** utilizzare un'enumerazione per tipizzare parametri, proprietà e restituiscono valori che rappresentano i set di valori.

**✓ DO** preferire l'utilizzo di un'enumerazione anziché costanti statiche.

**X DO NOT** utilizzare un tipo enum di set aperto (ad esempio la versione del sistema operativo, nomi degli amici, ecc.).

**X DO NOT** forniscono valori enum riservato che servono per utilizzi futuri.

È sempre possibile aggiungere semplicemente valori all'enum esistente in una fase successiva. Per ulteriori informazioni sull'aggiunta di valori alle enumerazioni, vedere [aggiunta di valori alle enumerazioni](#add_value) . I valori riservati non inquinano il set di valori reali e tendono a causare errori dell'utente.

**X AVOID** esporre pubblicamente le enumerazioni con un solo valore.

Una procedura comune per garantire l'estendibilità futura delle API C consiste nell'aggiungere parametri riservati alle firme dei metodi. Tali parametri riservati possono essere espressi come enum con un unico valore predefinito. Questa operazione non deve essere eseguita nelle API gestite. L'overload dei metodi consente l'aggiunta di parametri nelle versioni future.

**X DO NOT** includono valori sentinel nelle enumerazioni.

Sebbene siano talvolta utili per gli sviluppatori di Framework, i valori sentinella creano confusione per gli utenti del Framework. Vengono utilizzati per tenere traccia dello stato dell'enumerazione anziché di uno dei valori del set rappresentato dall'enumerazione.

**✓ DO** fornire un valore pari a zero sulle enumerazioni semplici.

Prendere in considerazione la chiamata di un valore simile a "None". Se tale valore non è appropriato per questa enumerazione specifica, il valore predefinito più comune per l'enumerazione deve essere assegnato al valore sottostante pari a zero.

**✓ CONSIDER** utilizzando <xref:System.Int32> (impostazione predefinita nella maggior parte dei linguaggi di programmazione) con il tipo sottostante di un'enumerazione, a meno che una delle seguenti è true:

- Enum è un'enumerazione Flags e sono presenti più di 32 flag oppure si prevede di avere più in futuro.

- Il tipo sottostante deve essere diverso da <xref:System.Int32> per semplificare l'interoperabilità con codice non gestito che prevede enum di dimensioni diverse.

- Un tipo sottostante più piccolo comporta un notevole risparmio nello spazio. Se si prevede che l'enumerazione venga utilizzata principalmente come argomento per il flusso di controllo, le dimensioni hanno poca differenza. Il risparmio di dimensioni può essere significativo se:

  - Si prevede che l'enumerazione venga utilizzata come campo in una struttura o una classe con un'istanza molto frequente.

  - Si prevede che gli utenti creino matrici o raccolte di grandi dimensioni delle istanze di enum.

  - Si prevede che un numero elevato di istanze dell'enum venga serializzato.

Per l'utilizzo in memoria, tenere presente che gli oggetti gestiti sono sempre allineati `DWORD`, quindi è necessario che in un'istanza siano presenti più enumerazioni o altre strutture di piccole dimensioni per comprimere un'enum più piccola con per fare una differenza, in quanto le dimensioni totali dell'istanza verranno sempre arrotondate per eccesso a una `DWORD`.

**✓ DO** denominare le enumerazioni di flag con plurale o sintagmi nominali e le enumerazioni semplici con singolare o sintagmi nominali.

**X DO NOT** estendere <xref:System.Enum?displayProperty=nameWithType> direttamente.

<xref:System.Enum?displayProperty=nameWithType> è un tipo speciale utilizzato da CLR per creare enumerazioni definite dall'utente. La maggior parte dei linguaggi di programmazione fornisce un elemento di programmazione che consente di accedere a questa funzionalità. Ad esempio, nella C# parola chiave `enum` viene usato per definire un'enumerazione.

<a name="design"></a>

### <a name="designing-flag-enums"></a>Progettazione di enumerazioni di flag

**✓ DO** applica il <xref:System.FlagsAttribute?displayProperty=nameWithType> per le enumerazioni di flag. Non applicare questo attributo alle enumerazioni semplici.

**✓ DO** utilizzano potenze di due per i valori di enumerazione flag pertanto possono essere liberamente combinati mediante un'operazione OR bit per bit.

**✓ CONSIDER** fornendo valori enum speciale per comunemente utilizzato le combinazioni di flag.

Le operazioni bit per bit sono un concetto avanzato e non devono essere necessarie per le attività semplici. <xref:System.IO.FileAccess.ReadWrite> è un esempio di tale valore speciale.

**X AVOID** creazione le enumerazioni di flag in cui non sono valide alcune combinazioni di valori.

**X AVOID** utilizzando flag valori enum pari a zero, a meno che il valore rappresenta "tutti i flag vengono cancellati" ed è denominato in modo appropriato, come stabilito dalla linea guida successiva.

**✓ DO** denominare il valore zero di enumerazioni di flag `None`. Per l'enumerazione di un flag, il valore deve sempre indicare che tutti i flag sono cancellati.

<a name="add_value"></a>

### <a name="adding-value-to-enums"></a>Aggiunta di un valore alle enumerazioni

È molto comune rilevare che è necessario aggiungere valori a un'enum dopo che è già stato spedito. Si verifica un potenziale problema di compatibilità delle applicazioni quando viene restituito il valore appena aggiunto da un'API esistente, perché le applicazioni scritte in modo non corretto potrebbero non gestire correttamente il nuovo valore.

**✓ CONSIDER** aggiunta di valori per le enumerazioni, nonostante un rischio per la compatibilità di piccole dimensioni.

Se sono presenti dati reali sulle incompatibilità delle applicazioni causati da aggiunte a un'enumerazione, è consigliabile aggiungere una nuova API che restituisce i valori nuovi e precedenti e deprecare l'API precedente, che dovrebbe continuare a restituire solo i valori precedenti. In questo modo le applicazioni esistenti rimarranno compatibili.

*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*

*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*

## <a name="see-also"></a>Vedere anche

- [Linee guida per la progettazione di tipi](../../../docs/standard/design-guidelines/type.md)
- [Linee guida per la progettazione di Framework](../../../docs/standard/design-guidelines/index.md)
