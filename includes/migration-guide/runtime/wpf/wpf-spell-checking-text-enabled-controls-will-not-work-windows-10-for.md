---
ms.openlocfilehash: 1d2e4a058008676c6ea85becebd4bb9220569ef3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621364"
---
### <a name="wpf-spell-checking-in-text-enabled-controls-will-not-work-in-windows-10-for-languages-not-in-the-oss-input-language-list"></a>Il controllo ortografico WPF nei controlli con supporto di testo non funziona in Windows 10 per le lingue non incluse nell'elenco lingue di input del sistema operativo

#### <a name="details"></a>Dettagli

Durante l'esecuzione in Windows 10, il controllo ortografico potrebbe non funzionare per i controlli WPF basati su testo perché le funzionalità di controllo ortografico della piattaforma sono disponibili solo per le lingue presenti nell'elenco delle lingue di input. In Windows 10, quando una lingua viene aggiunta all'elenco di tastiere disponibili, Windows scarica e installa automaticamente una funzione corrispondente nel pacchetto di funzionalità su richiesta (FOD, Feature on Demand) che offre funzionalità di controllo ortografico. Aggiungendo la lingua all'elenco di lingue di input, il controllo ortografico sarà supportato.

#### <a name="suggestion"></a>Suggerimento

Tenere presente che per il funzionamento del controllo ortografico in Windows 10 è necessario aggiungere la lingua o il testo da sottoporre a controllo come lingua di input.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.6|
|Type|Runtime|
