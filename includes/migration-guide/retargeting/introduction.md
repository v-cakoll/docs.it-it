## <a name="introduction"></a>Introduzione
Le modifiche di reindirizzamento influiscono sulle app che vengono ricompilate per una versione diversa di .NET Framework. e comprendono:

* Modifiche all'ambiente in fase di progettazione. Gli strumenti di compilazione, ad esempio, possono generare avvisi mentre in precedenza non lo facevano.

* Modifiche all'ambiente di runtime. Queste influiscono solo sulle app destinate specificamente a una versione diversa di .NET Framework. Le app destinate a versioni precedenti di .NET Framework si comportano come se venissero eseguite in tali versioni.

Negli argomenti che descrivono le modifiche di reindirizzamento i singoli elementi sono stati classificati in base all'impatto previsto, come descritto di seguito:

**Principale** Una modifica significativa che influisce su un numero elevato di app o che richiede variazioni sostanziali del codice.

**Secondario** Una modifica che influisce su un numero ridotto di app o che richiede variazioni marginali del codice.

**Caso limite** Una modifica che influisce sulle app in scenari molto specifici e non comuni.

**Trasparente** Una modifica che non ha effetti evidenti sullo sviluppatore o sull'utente dell'app. L'app non dovrebbe richiedere variazioni a causa di questa modifica.
