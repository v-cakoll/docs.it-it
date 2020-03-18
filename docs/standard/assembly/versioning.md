---
title: Controllo delle versioni degli assembly
ms.date: 08/20/2019
helpviewer_keywords:
- informational versions
- version numbers, assemblies
- assemblies [.NET Framework], versioning
- resolving assembly binding requests
- versioning, assemblies
ms.assetid: 775ad4fb-914f-453c-98ef-ce1089b6f903
ms.openlocfilehash: bbb3dae2ce66c93d05a2a1c0f7e426901fa7b2e0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73140186"
---
# <a name="assembly-versioning"></a>Controllo delle versioni degli assembly

Il controllo delle versioni degli assembly che utilizzano Common Language Runtime viene svolto interamente a livello dell'assembly. La specifica versione di un assembly e le versioni degli assembly dipendenti sono memorizzate nel manifesto dell'assembly. I criteri di versione predefiniti del runtime prevedono che l'applicazione venga eseguita solo con le versioni con cui è stata compilata e testata. Per modificare il comportamento predefinito, è possibile esprimere esplicitamente criteri di versione diversi nei file di configurazione (il file di configurazione dell'applicazione, il file dei criteri dell'autore e il file di configurazione dell'amministratore del computer).  
  
> [!NOTE]
> Il controllo delle versioni viene svolto solo su assembly con nomi sicuri.  
  
Per risolvere una richiesta di associazione di un assembly, il runtime compie diverse operazioni:  
  
1. Controlla il riferimento originale dell'assembly per determinare a quale versione dell'assembly effettuare l'associazione.  
  
2. Controlla tutti i file di configurazione interessati per adottare i criteri di versione prescritti.  
  
3. Sulla base del riferimento originale e di eventuali reindirizzamenti specificati nei file di configurazione, determina la versione dell'assembly da collegare all'assembly che ha effettuato la chiamata.  
  
4. Controlla la Global Assembly Cache, le codebase specificate nei file di configurazione, quindi controlla la directory e le sottodirectory dell'applicazione utilizzando le regole di sondaggio illustrate in [Come il runtime individua gli assembly](../../framework/deployment/how-the-runtime-locates-assemblies.md).  
  
Questi passaggi sono illustrati nella figura seguente:  
  
![Diagramma che illustra i passaggi della risoluzione della richiesta di associazione di un assembly.](./media/versioning/resolve-assembly-binding-request.gif)
  
Per ulteriori informazioni sulla configurazione delle applicazioni, vedere [Configurare le app](../../framework/configure-apps/index.md). Per ulteriori informazioni sui criteri di associazione, vedere [Come il runtime individua gli assembly](../../framework/deployment/how-the-runtime-locates-assemblies.md).  
  
## <a name="version-information"></a>Informazioni sulla versione  

In ciascun assembly le informazioni sulla versione sono espresse in due modi:  
  
- Il numero di versione dell'assembly, che insieme al nome dell'assembly e alle informazioni sulle impostazioni cultura è parte dell'identità dell'assembly. Tale numero viene utilizzato dal runtime per applicare i criteri di versione e gioca un ruolo determinante nel processo per la risoluzione dei tipi in fase di esecuzione.  
  
- Una versione informativa, cioè una stringa che riporta informazioni aggiuntive sulla versione a fini esclusivamente informativi.  
  
### <a name="assembly-version-number"></a>Numero di versione dell'assembly  

Tutti gli assembly hanno un numero di versione che concorre a definirne l'identità. Di conseguenza, due assembly che hanno numeri di versione differenti sono considerati dal runtime come due assembly distinti. Il numero di versione è rappresentato fisicamente da una stringa divisa in quattro parti, come indicato di seguito:  
  
\<*versione principale*>.\<*versione secondaria*>.\<*numero di build*>.\<*revisione*>  
  
Versione 1.5.1254.0 indica ad esempio 1 come numero di versione principale, 5 come numero di versione secondario, 1254 come numero di build e 0 come numero di revisione.  
  
Il numero di versione viene memorizzato nel manifesto dell'assembly insieme ad altre informazioni che contribuiscono a definire l'identità dell'assembly, tra cui il nome e la chiave pubblica, le informazioni sulle relazioni e le identità di altri assembly connessi all'applicazione.  
  
Quando si compila un assembly, lo strumento di sviluppo memorizza informazioni sulle dipendenze che riguardano ciascun assembly a cui si fa riferimento nel manifesto dell'assembly. Il runtime utilizza tali numeri di versione, insieme alle informazioni di configurazione impostate da un amministratore, un'applicazione o un autore, per caricare la versione corretta dell'assembly a cui si fa riferimento.  
  
Ai fini del controllo di versione, il runtime distingue tra assembly dotati o meno di nome sicuro. Il controllo di versione viene effettuato solo con assembly con nome sicuro.  
  
Per informazioni sulla specifica dei criteri di associazione delle versioni, vedere [Configurare le app.](../../framework/configure-apps/index.md) Per informazioni su come il runtime utilizza le informazioni sulla versione per trovare un determinato assembly, vedere [Come il runtime individua gli assembly](../../framework/deployment/how-the-runtime-locates-assemblies.md).  
  
### <a name="assembly-informational-version"></a>Versione informativa dell'assembly  

La versione informativa è una stringa che specifica ulteriori informazioni sulla versione di un assembly a fini esclusivamente informativi. Tali informazioni non vengono utilizzate in fase di esecuzione. La versione informativa espressa in testo semplice riporta informazioni commerciali, informazioni sul pacchetto o il nome del prodotto e non viene utilizzata dal runtime. Una versione informativa può ad esempio essere "Common Language Runtime, versione 1.0" o "NET Control SP 2". Nella scheda Versione della finestra di dialogo delle Proprietà file in Microsoft Windows queste informazioni sono visualizzate alla voce "Versione prodotto".  
  
> [!NOTE]
> Sebbene sia possibile specificare qualsiasi testo, se il formato della stringa non è quello utilizzato dal numero di versione dell'assembly o se il formato è corretto ma il testo contiene caratteri jolly, viene visualizzato un messaggio di avviso. L'avviso è puramente informativo.  
  
La versione informativa viene espressa utilizzando l'attributo personalizzato <xref:System.Reflection.AssemblyInformationalVersionAttribute?displayProperty=nameWithType>. Per ulteriori informazioni sull'attributo della versione informativa, vedere [Impostare gli attributi dell'assembly](set-attributes.md).  
  
## <a name="see-also"></a>Vedere anche

- [Come il runtime individua gli assembly](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [Configurazione di app](../../framework/configure-apps/index.md)
- [Impostare gli attributi dell'assembly](set-attributes.md)
- [Assembly in .NET](index.md)
