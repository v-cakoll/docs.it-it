---
title: Globalizzazione e ICU
ms.date: 05/21/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- globalization [.NET Framework], about globalization
- global applications, globalization
- international applications [.NET Framework], globalization
- world-ready applications, globalization
- application development [.NET Framework], globalization
- culture, globalization
- icu, icu on windows, ms-icu
ms.openlocfilehash: 6ea848d4a60069e6702b9d60fd90a55f572fb043
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842527"
---
# <a name="net-globalization-and-icu"></a>Globalizzazione .NET e ICU

In passato, le API di globalizzazione di .NET usavano librerie sottostanti diverse su piattaforme diverse. In UNIX, le API usavano i [componenti internazionali per Unicode (ICU)](http://site.icu-project.org/home)e in Windows hanno usato il [servizio NLS (National Language Support)](/windows/win32/intl/national-language-support). Ciò ha comportato alcune differenze di comportamento in alcune API di globalizzazione durante l'esecuzione di applicazioni su piattaforme diverse. Le differenze di comportamento sono evidenti in queste aree:

- Impostazioni cultura e dati delle impostazioni cultura
- Maiuscole/minuscole stringa
- Ordinamento e ricerca di stringhe
- Chiavi di ordinamento
- Normalizzazione delle stringhe
- Supporto dei nomi di dominio internazionalizzazione (IDN)
- Nome visualizzato del fuso orario in Linux

A partire da .NET 5,0, gli sviluppatori hanno un maggiore controllo sulla libreria sottostante, consentendo alle applicazioni di evitare differenze tra le diverse piattaforme.

## <a name="icu-on-windows"></a>ICU per Windows

Windows 10 May 2019 Update e versioni successive includono [ICU. dll](/windows/win32/intl/international-components-for-unicode--icu-) come parte del sistema operativo e .NET 5,0 e versioni successive usano ICU per impostazione predefinita. Quando è in esecuzione in Windows, .NET 5,0 e versioni successive tentano di caricare `icu.dll` e, se disponibile, lo usa per l'implementazione della globalizzazione.  Se non è possibile trovare o caricare la libreria, ad esempio quando si eseguono versioni precedenti di Windows, .NET 5,0 e versioni successive eseguono il fallback all'implementazione basata su NLS.

> [!NOTE]
> Anche quando si usa ICU, `CurrentCulture` i `CurrentUICulture` membri, e `CurrentRegion` usano ancora le API del sistema operativo Windows per rispettare le impostazioni utente.

### <a name="using-nls-instead-of-icu"></a>Uso di NLS anziché di ICU

L'uso di ICU anziché NLS può comportare differenze di comportamento con alcune operazioni correlate alla globalizzazione. Per ripristinare l'utilizzo di NLS, uno sviluppatore può rifiutare esplicitamente l'implementazione di ICU. Le applicazioni possono abilitare la modalità NLS in uno dei modi seguenti:

- Nel file di progetto:

```xml
<ItemGroup>
  <RuntimeHostConfigurationOption Include="System.Globalization.UseNls" Value="true" />
</ItemGroup>
```

- Nel file `runtimeconfig.json`:

```json
{
  "runtimeOptions": {
     "configProperties": {
       "System.Globalization.UseNls": true
      }
  }
}
```

- Impostando la variabile di ambiente sul `DOTNET_SYSTEM_GLOBALIZATION_USENLS` valore `true` o `1` .

> [!NOTE]
> Un valore impostato nel progetto o nel file ha `runtimeconfig.json` la precedenza sulla variabile di ambiente.

Per ulteriori informazioni, vedere [impostazioni di configurazione della fase di esecuzione](../../core/run-time-config/globalization.md#nls).

## <a name="app-local-icu"></a>App-ICU locale

Ogni versione di ICU può comportare correzioni di bug it, oltre ai dati CLDR (Common locale data repository) che descrivono le lingue del mondo. Il passaggio da una versione all'altra di ICU può influito leggermente sul comportamento dell'app quando si tratta di operazioni correlate alla globalizzazione.  Per consentire agli sviluppatori di applicazioni di garantire la coerenza tra tutte le distribuzioni, .NET 5,0 e versioni successive consentono alle app in Windows e UNIX di portare e usare la propria copia di ICU.

Le applicazioni possono acconsentire esplicitamente a una modalità di implementazione di un'applicazione ICU locale in uno dei modi seguenti:

- Nel file di progetto:

```xml
<ItemGroup>
  <RuntimeHostConfigurationOption Include="System.Globalization.AppLocalIcu" Value="<suffix>:<version> or <version>" />
</ItemGroup>
```

- Nel file `runtimeconfig.json`:

```json
{
  "runtimeOptions": {
     "configProperties": {
       "System.Globalization.AppLocalIcu": "<suffix>:<version> or <version>"
      }
  }
}
```

- Impostando la variabile di ambiente sul `DOTNET_SYSTEM_GLOBALIZATION_APPLOCALICU` valore `<suffix>:<version>` o `<version>` .

`<suffix>`: Suffisso facoltativo di lunghezza inferiore a 36 caratteri, che seguono le convenzioni di packaging di ICU pubblico. Quando si compila un ICU personalizzato, è possibile personalizzarlo per produrre i nomi di lib e i nomi dei simboli esportati in modo che contengano un suffisso, ad esempio, `libicuucmyapp` , dove `myapp` è il suffisso.

`<version>`: Versione di ICU valida, ad esempio 67,1. Questa versione viene usata per caricare i file binari e ottenere i simboli esportati.

Per caricare ICU quando si imposta l'opzione app-local, .NET usa il <xref:System.Runtime.InteropServices.NativeLibrary.TryLoad%2A?displayProperty=nameWithType> metodo, che esegue il probe di più percorsi. Il metodo tenta innanzitutto di trovare la libreria nella `NATIVE_DLL_SEARCH_DIRECTORIES` proprietà, creata dall'host DotNet in base al `deps.json` file per l'app. Per altre informazioni, vedere [Probe predefinito](../../core/dependency-loading/default-probing.md).

Per le app indipendenti, non è richiesta alcuna azione speciale da parte dell'utente, ad eccezione del fatto che ICU si trova nella directory dell'app (per le app autosufficienti, il valore predefinito della directory di lavoro è `NATIVE_DLL_SEARCH_DIRECTORIES` ).

Se usi ICU tramite un pacchetto NuGet, funziona in applicazioni dipendenti dal Framework. NuGet risolve gli asset nativi e li include nel `deps.json` file e nella directory di output per l'applicazione nella `runtimes` Directory. .NET lo carica da questa posizione.

Per le app dipendenti dal Framework (non indipendenti) in cui ICU viene utilizzato da una compilazione locale, è necessario eseguire passaggi aggiuntivi. .NET SDK non dispone ancora di una funzionalità per i file binari nativi "Loose" da incorporare in `deps.json` (vedere [questo problema SDK](https://github.com/dotnet/sdk/issues/11373)). In alternativa, è possibile abilitare questa operazione aggiungendo informazioni aggiuntive nel file di progetto dell'applicazione. ad esempio:

```xml
<ItemGroup>
  <IcuAssemblies Include="icu\*.so*" />
  <RuntimeTargetsCopyLocalItems Include="@(IcuAssemblies)" AssetType="native" CopyLocal="true" DestinationSubDirectory="runtimes/linux-x64/native/" DestinationSubPath="%(FileName)%(Extension)" RuntimeIdentifier="linux-x64" NuGetPackageId="System.Private.Runtime.UnicodeData" />
</ItemGroup>
```

Questa operazione deve essere eseguita per tutti i file binari di ICU per i runtime supportati. Inoltre, i `NuGetPackageId` metadati nel `RuntimeTargetsCopyLocalItems` gruppo di elementi devono corrispondere a un pacchetto NuGet a cui fa effettivamente riferimento il progetto.

### <a name="macos-behavior"></a>comportamento macOS

`macOS`ha un comportamento diverso per la risoluzione delle librerie dinamiche dipendenti dai comandi di caricamento specificati nel `match-o` file rispetto al caricatore Linux. Nel caricatore Linux, .NET può provare `libicudata` , `libicuuc` e `libicui18n` (in questo ordine) per soddisfare il grafico delle dipendenze di ICU. Tuttavia, in macOS questa operazione non funziona. Quando si compila ICU in macOS, per impostazione predefinita si ottiene una libreria dinamica con questi comandi di caricamento in `libicuuc` . Per esempio.:

```sh
~/ % otool -L /Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib
/Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib:
 libicuuc.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 libicudata.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 /usr/lib/libSystem.B.dylib (compatibility version 1.0.0, current version 1281.100.1)
 /usr/lib/libc++.1.dylib (compatibility version 1.0.0, current version 902.1.0)
```

Questi comandi fanno riferimento solo al nome delle librerie dipendenti per gli altri componenti di ICU. Il caricatore esegue la ricerca seguendo le `dlopen` convenzioni, che comporta la presenza di queste librerie nelle directory di sistema o l'impostazione di `LD_LIBRARY_PATH` env var oppure la presenza di ICU nella directory a livello di app. Se non è possibile impostare `LD_LIBRARY_PATH` o assicurarsi che i file binari di ICU si trovino nella directory a livello di app, è necessario eseguire alcune operazioni aggiuntive.

Sono disponibili alcune direttive per il caricatore, ad esempio `@loader_path` , che indicano al caricatore di cercare tale dipendenza nella stessa directory del file binario con il comando Load. A questo scopo è possibile procedere in due modi:

- `install_name_tool -change`

  Eseguire i comandi seguenti:

```bash
install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicuuc.67.1.dylib
install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicui18n.67.1.dylib
install_name_tool -change "libicuuc.67.dylib" "@loader_path/libicuuc.67.dylib" /path/to/libicui18n.67.1.dylib
```

- Patch ICU per produrre i nomi di installazione con`@loader_path`

  Prima di eseguire autoconf ( `./runConfigureICU` ), modificare [le righe seguenti](https://github.com/unicode-org/icu/blob/ef91cc3673d69a5e00407cda94f39fcda3131451/icu4c/source/config/mh-darwin#L32-L37) in:

```
LD_SONAME = -Wl,-compatibility_version -Wl,$(SO_TARGET_VERSION_MAJOR) -Wl,-current_version -Wl,$(SO_TARGET_VERSION) -install_name @loader_path/$(notdir $(MIDDLE_SO_TARGET))
```
