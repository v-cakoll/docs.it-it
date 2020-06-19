---
title: Usare code coverage per unit test
description: Informazioni su come usare le funzionalità di code coverage per gli unit test .NET.
author: IEvangelist
ms.author: dapine
ms.date: 06/16/2020
ms.openlocfilehash: 47f10ae367f511d5d02d32bfcb35bf4775a3e946
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990279"
---
# <a name="use-code-coverage-for-unit-testing"></a>Usare code coverage per unit test

Gli unit test consentono di garantire la funzionalità e forniscono un mezzo di verifica per eseguire il refactoring. Il code coverage è una misura della quantità di codice eseguito dagli unit test, ovvero linee, rami o metodi. Ad esempio, se si dispone di un'applicazione semplice con solo due rami condizionali di codice (_Branch a_e _Branch b_), un unit test che verifica il ramo condizionale _a_ restituirà un ramo code coverage del 50%.

Questo articolo illustra l'uso di code coverage per unit test con copriletto e la generazione di report con ReportGenerator. Sebbene questo articolo sia incentrato su C# e xUnit come Framework di test, anche MSTest e NUnit funzioneranno. Copriletto è un [progetto open source su GitHub](https://github.com/coverlet-coverage/coverlet) che fornisce un framework di code coverage multipiattaforma per C#. [Copriletto](https://dotnetfoundation.org/projects/coverlet) fa parte di .NET Foundation. Copriletto raccoglie i dati di esecuzione dei test di code coverage Cobertura, usati per la generazione di report.

Inoltre, in questo articolo viene illustrato come utilizzare le informazioni code coverage raccolte da un'esecuzione di test di copriletto per generare un report. La generazione di report è possibile usando un altro [progetto open source in GitHub-ReportGenerator](https://github.com/danielpalme/ReportGenerator). ReportGenerator converte i report di code coverage generati da cobertura tra molti altri in report leggibili in vari formati.

## <a name="system-under-test"></a>Sistema sottoposto a test

Il "sistema sottoposto a test" si riferisce al codice su cui si sta scrivendo unit test, potrebbe trattarsi di un oggetto, di un servizio o di qualsiasi altro elemento che espone la funzionalità testabile. Ai fini di questo articolo verrà creata una libreria di classi che sarà il sistema sottoposto a test e due progetti di unit test corrispondenti.

### <a name="create-a-class-library"></a>Creare una libreria di classi

Da un prompt dei comandi in una nuova directory denominata `UnitTestingCodeCoverage` , creare una nuova libreria di classi .NET standard usando il [`dotnet new classlib`](../tools/dotnet-new.md#classlib) comando:

```dotnetcli
dotnet new classlib -n Numbers
```

Il frammento di codice seguente definisce una semplice `PrimeService` classe che fornisce la funzionalità per verificare se un numero è un numero primo. Copiare il frammento di codice seguente e sostituire il contenuto del file *Class1.cs* creato automaticamente nella directory *numbers* . Rinominare il file *Class1.cs* in *PrimeService.cs*.

```csharp
namespace System.Numbers
{
    public class PrimeService
    {
        public bool IsPrime(int candidate)
        {
            if (candidate < 2)
            {
                return false;
            }

            for (int divisor = 2; divisor <= Math.Sqrt(candidate); ++divisor)
            {
                if (candidate % divisor == 0)
                {
                    return false;
                }
            }
            return true;
        }
    }
}
```

> [!TIP]
> Vale la pena menzionare che la `Numbers` libreria di classi è stata intenzionalmente aggiunta allo `System` spazio dei nomi. <xref:System.Math?displayProperty=fullName>In questo modo è possibile accedere a senza una `using System;` dichiarazione dello spazio dei nomi. Per altre informazioni, vedere [Namespace (riferimenti per C#)](../../csharp/language-reference/keywords/namespace.md).

### <a name="create-test-projects"></a>Creazione di progetti di test

Creare due nuovi modelli di **progetto di test di xUnit (.NET Core)** dallo stesso prompt dei comandi usando il [`dotnet new xunit`](../tools/dotnet-new.md#test) comando:

```dotnetcli
dotnet new xunit -n XUnit.Coverlet.Collector
```

```dotnetcli
dotnet new xunit -n XUnit.Coverlet.MSBuild
```

Entrambi i progetti di test xUnit appena creati devono aggiungere un riferimento al progetto della libreria di classi *numbers* . In questo modo, i progetti di test possono accedere a *PrimeService* per il test. Al prompt dei comandi usare il [`dotnet add`](../tools/dotnet-add-reference.md) comando:

```dotnetcli
dotnet add XUnit.Coverlet.Collector\XUnit.Coverlet.Collector.csproj reference Numbers\Numbers.csproj
```

```dotnetcli
dotnet add XUnit.Coverlet.MSBuild\XUnit.Coverlet.MSBuild.csproj reference Numbers\Numbers.csproj
```

Il progetto *MSBuild* è denominato in modo appropriato, in quanto dipende dal pacchetto NuGet [copriletto. MSBuild](https://www.nuget.org/packages/coverlet.msbuild) . Aggiungere questa dipendenza del pacchetto eseguendo il [`dotnet add package`](../tools/dotnet-add-package.md) comando:

```dotnetcli
cd XUnit.Coverlet.MSBuild && dotnet add package coverlet.msbuild && cd ..
```

Il comando precedente ha modificato le directory in modo efficace nell'ambito del progetto di test *MSBuild* , quindi ha aggiunto il pacchetto NuGet. Al termine di questa operazione, le directory vengono modificate e viene eseguito il backup di un livello.

Aprire entrambi i file *UnitTest1.cs* e sostituirne il contenuto con il frammento di codice seguente. Rinominare i file *UnitTest1.cs* in *PrimeServiceTests.cs*.

```csharp
using System.Numbers;
using Xunit;

namespace XUnit.Coverlet
{
    public class PrimeServiceTests
    {
        readonly PrimeService _primeService;

        public PrimeServiceTests() => _primeService = new PrimeService();

        [
            Theory,
            InlineData(-1), InlineData(0), InlineData(1)
        ]
        public void IsPrime_ValuesLessThan2_ReturnFalse(int value) =>
            Assert.False(_primeService.IsPrime(value), $"{value} should not be prime");

        [
            Theory,
            InlineData(2), InlineData(3), InlineData(5), InlineData(7)
        ]
        public void IsPrime_PrimesLessThan10_ReturnTrue(int value) =>
            Assert.True(_primeService.IsPrime(value), $"{value} should be prime");

        [
            Theory,
            InlineData(4), InlineData(6), InlineData(8), InlineData(9)
        ]
        public void IsPrime_NonPrimesLessThan10_ReturnFalse(int value) =>
            Assert.False(_primeService.IsPrime(value), $"{value} should not be prime");
    }
}
```

### <a name="create-a-solution"></a>Creare una soluzione

Al prompt dei comandi, creare una nuova soluzione per incapsulare la libreria di classi e i due progetti di test. Utilizzando il [`dotnet sln`](../tools/dotnet-sln.md) comando:

```dotnetcli
dotnet new sln -n XUnit.Coverage
```

Verrà creato un nuovo nome del file `XUnit.Coverage` di soluzione nella directory *UnitTestingCodeCoverage* Aggiungere i progetti alla radice della soluzione.

## <a name="linux"></a>[Linux](#tab/linux)

```dotnetcli
dotnet sln XUnit.Coverage.sln add **/*.csproj --in-root
```

## <a name="windows"></a>[Windows](#tab/windows)

```dotnetcli
dotnet sln XUnit.Coverage.sln add (ls **/*.csproj) --in-root
```

---

Compilare la soluzione usando il [`dotnet build`](../tools/dotnet-build.md) comando:

```dotnetcli
dotnet build
```

Se la compilazione ha esito positivo, sono stati creati i tre progetti, i progetti e i pacchetti a cui si fa riferimento in modo appropriato e il codice sorgente è stato aggiornato correttamente. Ecco fatto!

## <a name="tooling"></a>Strumenti

Esistono due tipi di strumenti di code coverage:

- Agenti di **raccolta dati:** I DataCollectors monitorano l'esecuzione dei test e raccolgono informazioni sulle esecuzioni dei test. Segnalano le informazioni raccolte in diversi formati di output, ad esempio XML e JSON. Per ulteriori informazioni, vedere [il primo DataCollector](https://github.com/Microsoft/vstest-docs/blob/master/docs/extensions/datacollector.md).
- **Generatori di report:** Usare i dati raccolti dalle esecuzioni dei test per generare report, spesso come HTML con stile.

In questa sezione lo stato attivo si concentra sugli strumenti di raccolta dati. Per usare copriletto per code coverage, un progetto di unit test esistente deve avere le dipendenze del pacchetto appropriate o, in alternativa, basarsi sugli [strumenti globali .NET](../tools/global-tools.md) e sul pacchetto NuGet [copriletto. console](https://www.nuget.org/packages/coverlet.console) corrispondente.

## <a name="integrate-with-net-test"></a>Eseguire l'integrazione con test .NET

Il modello di progetto di test xUnit si integra già con [copriletto. Collector](https://www.nuget.org/packages/coverlet.collector) per impostazione predefinita.
Al prompt dei comandi passare alla directory del progetto *xUnit. copriletto. Collector* ed eseguire il [`dotnet test`](../tools/dotnet-test.md) comando:

```dotnetcli
cd XUnit.Coverlet.Collector && dotnet test --collect:"XPlat Code Coverage"
```

> [!NOTE]
> L' `"XPlat Code Coverage"` argomento è un nome descrittivo che corrisponde agli agenti di raccolta dati da copriletto. Questo nome è obbligatorio, ma non fa distinzione tra maiuscole e minuscole.

Come parte dell' `dotnet test` esecuzione, un file di *coverage.cobertura.xml* risultante viene restituito alla directory *TestResults* Il file XML contiene i risultati. Si tratta di un'opzione multipiattaforma che si basa sul interfaccia della riga di comando di .NET Core ed è ideale per i sistemi di compilazione in cui MSBuild non è disponibile.

Di seguito è riportato il file di esempio *coverage.cobertura.xml* .

```xml
<?xml version="1.0" encoding="utf-8"?>
<coverage line-rate="1" branch-rate="1" version="1.9" timestamp="1592248008"
          lines-covered="12" lines-valid="12" branches-covered="6" branches-valid="6">
  <sources>
    <source>C:\</source>
  </sources>
  <packages>
    <package name="Numbers" line-rate="1" branch-rate="1" complexity="6">
      <classes>
        <class name="Numbers.PrimeService" line-rate="1" branch-rate="1" complexity="6"
               filename="Numbers\PrimeService.cs">
          <methods>
            <method name="IsPrime" signature="(System.Int32)" line-rate="1"
                    branch-rate="1" complexity="6">
              <lines>
                <line number="8" hits="11" branch="False" />
                <line number="9" hits="11" branch="True" condition-coverage="100% (2/2)">
                  <conditions>
                    <condition number="7" type="jump" coverage="100%" />
                  </conditions>
                </line>
                <line number="10" hits="3" branch="False" />
                <line number="11" hits="3" branch="False" />
                <line number="14" hits="22" branch="True" condition-coverage="100% (2/2)">
                  <conditions>
                    <condition number="57" type="jump" coverage="100%" />
                  </conditions>
                </line>
                <line number="15" hits="7" branch="False" />
                <line number="16" hits="7" branch="True" condition-coverage="100% (2/2)">
                  <conditions>
                    <condition number="27" type="jump" coverage="100%" />
                  </conditions>
                </line>
                <line number="17" hits="4" branch="False" />
                <line number="18" hits="4" branch="False" />
                <line number="20" hits="3" branch="False" />
                <line number="21" hits="4" branch="False" />
                <line number="23" hits="11" branch="False" />
              </lines>
            </method>
          </methods>
          <lines>
            <line number="8" hits="11" branch="False" />
            <line number="9" hits="11" branch="True" condition-coverage="100% (2/2)">
              <conditions>
                <condition number="7" type="jump" coverage="100%" />
              </conditions>
            </line>
            <line number="10" hits="3" branch="False" />
            <line number="11" hits="3" branch="False" />
            <line number="14" hits="22" branch="True" condition-coverage="100% (2/2)">
              <conditions>
                <condition number="57" type="jump" coverage="100%" />
              </conditions>
            </line>
            <line number="15" hits="7" branch="False" />
            <line number="16" hits="7" branch="True" condition-coverage="100% (2/2)">
              <conditions>
                <condition number="27" type="jump" coverage="100%" />
              </conditions>
            </line>
            <line number="17" hits="4" branch="False" />
            <line number="18" hits="4" branch="False" />
            <line number="20" hits="3" branch="False" />
            <line number="21" hits="4" branch="False" />
            <line number="23" hits="11" branch="False" />
          </lines>
        </class>
      </classes>
    </package>
  </packages>
</coverage>
```

> [!TIP]
> In alternativa, è possibile usare il pacchetto MSBuild se il sistema di compilazione usa già MSBuild. Al prompt dei comandi passare alla directory del progetto *xUnit. copriletto. MSBuild* ed eseguire il `dotnet test` comando:
>
> ```dotnetcli
> dotnet test --collect:"XPlat Code Coverage"
> ```
>
> Il file di *coverage.cobertura.xml* risultante è output.

## <a name="generate-reports"></a>Generare report

Ora che si è in grado di raccogliere dati da esecuzioni di unit test, è possibile generare report usando [ReportGenerator](https://github.com/danielpalme/ReportGenerator). Per installare il pacchetto NuGet [ReportGenerator](https://www.nuget.org/packages/dotnet-reportgenerator-globaltool) come [strumento globale .NET](../tools/global-tools.md), usare il [`dotnet tool install`](../tools/dotnet-tool-install.md) comando:

```dotnetcli
dotnet tool install -g dotnet-reportgenerator-globaltool
```

Eseguire lo strumento e specificare le opzioni desiderate, in base al file di output *coverage.cobertura.xml* dall'esecuzione dei test precedente.

```console
reportgenerator
"-reports:Path\To\TestProject\TestResults\{guid}\coverage.cobertura.xml"
"-targetdir:coveragereport"
-reporttypes:Html
```

Dopo l'esecuzione di questo comando, un file HTML rappresenta il report generato.

:::image type="content" source="media/test-report.png" lightbox="media/test-report.png" alt-text="Unit test-report generato":::

## <a name="see-also"></a>Vedere anche

- [Copertura del unit test di Visual Studio](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested)
- [Repository GitHub-copriletto](https://github.com/coverlet-coverage/coverlet)
- [Repository GitHub-ReportGenerator](https://github.com/danielpalme/ReportGenerator)
- [Sito del progetto ReportGenerator](https://danielpalme.github.io/ReportGenerator)
- [Comando interfaccia della riga di comando di .NET Core test](../tools/dotnet-test.md)

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Procedure consigliate per gli unit test](unit-testing-best-practices.md)
