---
title: Elementi obsoleti in .NET FrameworkWhat's obsolete in .NET Framework
ms.custom: updateeachrelease
ms.date: 04/02/2019
helpviewer_keywords:
- obsolete [.NET Framework]
- what's obsolete [.NET Framework]
- deprecated [.NET Framework]
ms.assetid: d356a43a-73df-4ae2-a457-b9628074c7cd
ms.openlocfilehash: 7cfebfde859a95495e9d2d5e42bd034ad5d55e61
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79143135"
---
# <a name="whats-obsolete-in-the-net-framework-class-library"></a>Elementi obsoleti nella libreria di classi .NET Framework

.NET cambia nel tempo. In ogni nuova versione vengono aggiunti nuovi tipi e membri dei tipi che forniscono nuove funzionalità. Anche i tipi esistenti e i relativi membri cambiano nel tempo. Ad esempio, alcuni tipi diventano meno importanti in quanto la tecnologia che supportano viene sostituita da una nuova tecnologia e alcuni metodi sono sostituiti da metodi più recenti che sono superiori in qualche modo.

.NET Framework e Common Language Runtime si sforzano di supportare la compatibilità con le versioni precedenti (consentendo alle applicazioni sviluppate con una versione di .NET Framework di essere eseguite nella versione successiva di .NET Framework). Ciò rende difficile la semplice rimozione di un tipo o di un membro del tipo. Al contrario, .NET indica che un tipo o un membro di tipo non deve più essere utilizzato contrassegnandolo come obsoleto o deprecato. La deprecazione di un tipo o di un membro ne implica il contrassegno, in modo che gli sviluppatori sappiano che verrà rimosso e abbiano il tempo di rispondere a tale rimozione. Tuttavia, il codice esistente che utilizza il tipo o membro continua a essere eseguito nella nuova versione di .NET.

> [!NOTE]
> I termini *obsoleti* e *deprecati* hanno lo stesso significato se applicati a tipi e membri .NET.

## <a name="the-obsoleteattribute-attribute"></a>Attributo ObsoleteAttribute

.NET Framework indica che un tipo o un membro del tipo è obsoleto contrassegnandolo con l'attributo <xref:System.ObsoleteAttribute>. L'applicazione dell'attributo a un tipo o un membro indica che quel tipo o membro verrà rimosso in una versione futura di .NET Framework, senza causare interruzioni nel codice compilato che lo usa.

Oltre a indicare che un tipo o un membro del tipo è obsoleto, <xref:System.ObsoleteAttribute> definisce il modo in cui il compilatore gestisce il codice sorgente che include quel tipo o membro. Il compilatore può compilare il codice generando però un messaggio di avviso oppure può considerare l'uso del tipo o membro come un errore. Nel primo caso, il codice può essere compilato correttamente, ma un messaggio di avviso indica che il tipo o membro è obsoleto. Nel secondo caso, la compilazione non riesce.

Anche se la compilazione produce un errore anziché un messaggio di avviso, <xref:System.ObsoleteAttribute> non influisce sul comportamento in fase di esecuzione. In altre parole, le applicazioni che usano il tipo o membro e che sono state compilate correttamente verranno sempre eseguite correttamente. Soltanto il tentativo di ricompilare un'applicazione che usa il tipo o membro avrà esito negativo.

## <a name="how-to-handle-obsolete-types-and-members"></a>Come gestire tipi e membri obsoleti

Quando si aggiorna e si ricompila il codice esistente, l'uso di un tipo o membro obsoleto che genera un avviso del compilatore nell'applicazione è perfettamente accettabile. Tuttavia, è consigliabile rivedere il messaggio di avviso del compilatore per stabilire se sia opportuno modificare il codice dell'applicazione. Se il messaggio non indica un'alternativa adatta, adottare una delle soluzioni seguenti:

- Modificare il codice rimuovendo l'uso del tipo o membro, se possibile.

     -oppure-

- Rivedere la documentazione di quest'area tecnologica per stabilire come rispondere a questa deprecazione.

Si può scegliere di non ricompilare il codice esistente con una versione successiva di .NET Framework. È possibile invece specificare la versione di .NET Framework con la quale eseguire il codice compilato esistente. Si supponga ad esempio di avere un'applicazione denominata app1.exe, compilata con .NET Framework 3.5 e di voler eseguire l'applicazione in .NET Framework 4.5. La procedura da adottare è la seguente:

1. Creare un file di configurazione per l'eseguibile principale e denominarlo *NomeApp*.exe.config, dove *NomeApp* è il nome dell'eseguibile dell'applicazione. Per l'applicazione denominata *app1.exe* nell'esempio, è necessario creare un file di configurazione denominato *app1.exe.config*.

2. Aggiungere il codice seguente al file di configurazione.

    ```xml
    <configuration>
       <startup>
          <supportedRuntime version="v4.0" />
       </startup>
    </configuration>
    ```

Per impostare come destinazione una versione specifica di .NET `version` Framework, assegnare uno dei seguenti valori stringa all'attributo:

|Versione di .NET Framework|Stringa `version`|
|-|-|
|4.8|v4.0|
|4.7 (incluse 4.7.1 e 4.7.2)|v4.0|
|4.6 (incluse 4.6.1 e 4.6.2)|v4.0|
|4.5 (incluse 4.5.1 e 4.5.2)|v4.0|
|4|v4.0|
|3,5|v2.0.50727|
|2.0|v2.0.50727|
|1.1|v1.1.4322|
|1.0|v1.0.3705|

## <a name="obsolete-apis-for-net-framework-45-and-later-versions"></a>API obsolete per .NET Framework 4.5 e versioni successive

- [Tipi obsoleti](obsolete-types.md)
- [Membri obsoleti](obsolete-members.md)

## <a name="obsolete-apis-for-previous-versions"></a>API obsolete per le versioni precedenti

- [Tipi obsoleti in .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee461503(v=vs.100))
- [Membri obsoleti in .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee471421(v=vs.100))
- [Elenco degli elementi obsoleti di .NET Framework 3.5](https://docs.microsoft.com/previous-versions/cc835481(v=msdn.10))
- [Elenco degli elementi obsoleti di .NET Framework 2.0](https://docs.microsoft.com/previous-versions/aa497286(v=msdn.10))

## <a name="see-also"></a>Vedere anche

- [\<supportedRuntime> elemento](../configure-apps/file-schema/startup/supportedruntime-element.md)
