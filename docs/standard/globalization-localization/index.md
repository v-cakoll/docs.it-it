---
title: Globalizzazione e localizzazione di applicazioni .NET
ms.date: 06/08/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- international applications [.NET]
- globalization [.NET], encoding
- global applications
- internationalization
- world-ready applications
- application development [.NET], globalization
- multilingual application development
ms.assetid: 9a59696b-d89b-45bd-946d-c75da4732d02
ms.openlocfilehash: 10d07a02a7ff744a87b920fd97df24b076c22cc3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288290"
---
# <a name="globalizing-and-localizing-net-applications"></a>Globalizzazione e localizzazione di applicazioni .NET

Lo sviluppo di applicazioni internazionali, tra cui un'applicazione che può essere localizzata in una o più lingue, include tre passaggi: globalizzazione, analisi della localizzabilità e localizzazione.

[Globalizzazione](globalization.md)

Questo passaggio implica la progettazione e la codifica di un'applicazione indipendente dalle impostazioni cultura e dalla lingua che supporti le interfacce utente e i dati internazionali localizzati per tutti gli utenti. Comporta decisioni di progettazione e programmazione non basate su presupposti impostazioni cultura specifiche. Quando un'applicazione globalizzata non viene localizzata, è tuttavia progettata e scritta in modo da poter essere successivamente localizzata in una o più lingue in modo relativamente semplice.

[Revisione della localizzabilità](localizability-review.md)

Questo passaggio prevede la revisione del codice e del progetto di un'applicazione per verificare che possa essere localizzata facilmente e per identificare potenziali problemi per la localizzazione e la verifica che il codice eseguibile dell'applicazione sia separato dalle relative risorse. Se la fase di globalizzazione ha avuto effetto, l'analisi della localizzabilità confermerà le scelte di codifica e di progettazione effettuate durante la globalizzazione. La fase di localizzabilità può inoltre identificare eventuali problemi rimanenti. In questo modo, il codice sorgente di un'applicazione non deve necessariamente essere modificato durante la fase di localizzazione.

[Localizzazione](localization.md)

Questo passaggio prevede la personalizzazione di un'applicazione per impostazioni cultura e aree specifiche. Se i passaggi di globalizzazione e possibilità di localizzazione sono stati eseguiti correttamente, la localizzazione consiste principalmente nella traduzione dell'interfaccia utente.

Se si ci attiene ai seguenti tre passaggi verranno offerti due vantaggi:

- In questo modo, non è necessario adattare un'applicazione progettata per supportare singole lingue, ad esempio Inglese US (Stati Uniti), per supportare le lingue aggiuntive.

- Restituisce applicazioni localizzate che sono più stabile e con meno bug.

In .NET viene fornito ampio supporto per lo sviluppo di applicazioni internazionali e localizzate. In particolare, molti membri del tipo nella libreria di classi .NET facilitano la globalizzazione restituendo valori che riflettono le convenzioni delle impostazioni cultura dell'utente o di impostazioni cultura specifiche. .NET supporta inoltre gli assembly satellite che semplificano il processo di localizzazione di un'applicazione.

Per altre informazioni, vedere la [documentazione sulla globalizzazione](/globalization/).

## <a name="in-this-section"></a>Contenuto della sezione

[Globalizzazione](globalization.md)

Viene descritta la prima fase di creazione di un'applicazione internazionale, che include la progettazione e la codifica di un'applicazione indipendente dalla lingua e dalle impostazioni cultura.

[Globalizzazione .NET e ICU](globalization-icu.md)

Viene descritto in che modo la globalizzazione di .NET usa [i componenti internazionali per Unicode (ICU)](http://site.icu-project.org/home).

[Revisione della localizzabilità](localizability-review.md)

Viene descritta la seconda fase di creazione di un'applicazione localizzata, che include l'identificazione dei potenziali blocchi stradali per la localizzazione.

[Localizzazione](localization.md)

Viene illustrata la fase finale della creazione di un'applicazione localizzata, che include la personalizzazione di un'interfaccia utente dell'applicazione per le aree o le impostazioni cultura specifiche.

[Operazioni sulle stringhe indipendenti dalle impostazioni cultura](culture-insensitive-string-operations.md)

Viene descritto come usare metodi e classi di .NET definiti come dipendenti dalle impostazioni cultura per impostazione predefinita per ottenere risultati indipendenti dalle impostazioni cultura.

[Procedure consigliate per lo sviluppo di applicazioni internazionali](best-practices-for-developing-world-ready-apps.md)

Vengono forniti alcuni suggerimenti per la globalizzazione, la localizzazione e lo sviluppo di applicazioni ASP.NET internazionali.

## <a name="reference"></a>Informazioni di riferimento

- Spazio dei nomi <xref:System.Globalization?displayProperty=nameWithType>

   Contiene classi che definiscono informazioni sulle impostazioni cultura, tra cui la lingua, il paese, il calendario, il formato delle date, delle valute e dei numeri e il criterio di ordinamento delle stringhe.

- Spazio dei nomi <xref:System.Resources>

   Vengono fornite le classi per la creazione, la manipolazione e l'uso di risorse.

- Spazio dei nomi <xref:System.Text>

   Contiene le classi che rappresentano le codifiche dei caratteri ASCII, ANSI, Unicode e altri tipi di codifiche.

- [Resgen. exe (Generatore di file di risorse)](../../framework/tools/resgen-exe-resource-file-generator.md)

   Viene descritto l'utilizzo di Resgen.exe per convertire i file con estensione txt e resx (formato risorse basato su XML) in file binari con estensione resources di Common Language Runtime.

- [Winres. exe (editor di risorse Windows Forms)](../../framework/tools/winres-exe-windows-forms-resource-editor.md)

   Viene descritto l'uso di Winres.exe per localizzare i form di Windows Form.
