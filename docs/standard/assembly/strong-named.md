---
title: Assembly con nomi sicuri
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, about strong-named assemblies
- assemblies [.NET Framework], strong-named
ms.assetid: d4a80263-f3e0-4d81-9b61-f0cbeae3797b
ms.openlocfilehash: 12b8df3195b2708e4556d4f8065227054db9eb14
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711571"
---
# <a name="strong-named-assemblies"></a>Assembly con nomi sicuri

L'assegnazione di un nome sicuro a un assembly permette di creare un'identità univoca e prevenire gli eventuali conflitti con altri assembly.

## <a name="what-makes-a-strong-named-assembly"></a>Come si genera un assembly con nome sicuro?

Per generare un assembly con nome sicuro usare la chiave privata corrispondente alla chiave pubblica distribuita con l'assembly, oltre all'assembly stesso. L'assembly include il relativo manifesto, che a sua volta contiene i nomi e gli hash di tutti i file che costituiscono l'assembly. Gli assembly che hanno lo stesso nome sicuro devono essere uguali.

È possibile assegnare nomi sicuri agli assembly usando Visual Studio o uno strumento da riga di comando. Per altre informazioni, vedere [procedura: firmare un assembly con un nome sicuro](sign-strong-name.md) o [sn. exe (strumento nome sicuro)](../../framework/tools/sn-exe-strong-name-tool.md).

Nel creare un assembly con nome sicuro è necessario includere il nome in formato testo semplice dell'assembly, il numero di versione, le informazioni facoltative relative alle impostazioni cultura, una firma digitale e la chiave pubblica corrispondente alla chiave privata usata per apporre la firma.

> [!WARNING]
> Non usare i nomi sicuri per la sicurezza, poiché forniscono solo un'identità univoca.

## <a name="why-strong-name-your-assemblies"></a>Perché assegnare nomi sicuri agli assembly?

Quando si fa riferimento a un assembly con nome sicuro, ci si aspettano determinate garanzie, quali il controllo delle versioni e la protezione dei nomi. Nel .NET Framework, gli assembly con nome sicuro possono essere installati nel Global Assembly Cache, che è necessario per abilitare alcuni scenari.

Gli assembly con nome sicuro risultano utili negli scenari seguenti:

- Per abilitare il riferimento agli assembly da parte degli assembly con nome sicuro o per concedere a un `friend` l'accesso all'assembly da altri assembly con nome sicuro.

- Un'app deve accedere a versioni diverse dello stesso assembly. Ciò significa che sono necessarie più versioni di un assembly da caricare affiancate nello stesso dominio di app senza conflitti. Ad esempio , se negli assembly esistono estensioni differenti di una API con lo stesso nome semplice, l'assegnazione di un nome sicuro consente di fornire un'identità univoca a ciascuna versione dell'assembly.

- Non si vuole influire negativamente sulle prestazioni delle app usando il proprio assembly, quindi si usa un assembly indipendente dal dominio. Questo richiede l'uso di nomi sicuri perché gli assembly indipendenti dal dominio devono essere installati in Global Assembly Cache.

- Si vuole centralizzare la manutenzione per l'app applicando i criteri dell'editore, che significa che l'assembly deve essere installato nella Global Assembly Cache.

Se si è uno sviluppatore open source e si desiderano i vantaggi di identità di un assembly con nome sicuro, è consigliabile archiviare la chiave privata associata a un assembly nel sistema di controllo del codice sorgente.

## <a name="see-also"></a>Vedere anche

- [Assembly Cache globale](../../framework/app-domains/gac.md)
- [Procedura: firmare un assembly con un nome sicuro](sign-strong-name.md)
- [Sn. exe (strumento nome sicuro)](../../framework/tools/sn-exe-strong-name-tool.md)
- [Creazione e utilizzo di assembly con nome sicuro](create-use-strong-named.md)
