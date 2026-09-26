# design/phase4 — manifest

Read-only copy of the approved Phase 4 design (07 Decision 45, approved by Karim 2026-09-26).
Source: Claude Design canvas https://claude.ai/artifact/PaSoos61b5By1yqdmUK1JM, version `1790413092-0523` (07 D42). Copied unchanged on 2026-09-26.

- The canvas is the original; this folder is its copy. A file whose sha256 differs from the list below is **not** the approved design — stop and ask (CLAUDE.md §6).
- 68 boards (the list in Build Spec §2) + `tokens.css` (sha256 must equal 07 D42). Not copied: session-1 boards (`A*`, `B*`, `C*`, `Issues`), `P1-A-Audit`, `Main` — history, not the approved design.
- Each board links `./tokens.css` (present) and `./support.js` (the canvas runtime — not copied). Read boards as HTML markup: layout, role tokens, words, ARIA roles. Words come from the string files, behaviour from the Build Spec (Build Spec §2, "What a frame is").
- Check: `sha256sum -c MANIFEST.sha256` in this folder.

| File | Bytes | sha256 |
|---|---:|---|
| `tokens.css` | 16456 | `fd09cb17c72ce208eb10baef724111b9db76fb279871bb8a6748bd641645f80e` |
| `P1-01-Orientation-1440.dc.html` | 28315 | `00d0fcc8c482ee7f7c3308c5ea2c1b2a4feae5ae1bb64c458b7d3ffd09c23832` |
| `P1-01-Orientation-390.dc.html` | 25669 | `30ebc929adc72604c7451c6f39f4d456fc9d1e61f51b094d2c5d325c424d5ea7` |
| `P1-02-Learning-1440.dc.html` | 15267 | `6ba808555d1bd2d4cfac248ad400fa9e41c5a0917669ef42bfd0bfe8b6272c48` |
| `P1-02-Learning-390.dc.html` | 12121 | `3caa6ffccb7653ce78751853b25cbecde4802bfaed8e83fc2dfde18ceb70e644` |
| `P1-03-Ghost-1440.dc.html` | 20264 | `0627c59a5f475b28aec429985f9f288587df8e0e2b33c1fbf0a5088ecf68928c` |
| `P1-03-Ghost-390.dc.html` | 14115 | `559306b950f6291a0326d8b14e4a3e2a19603747d15214df4227395bef8fd247` |
| `P1-04a-Practice-A-1440.dc.html` | 25839 | `02bafaa17bfb9dcf19624ba33aa77781abcd5aa625d9ab24ffa033b76865a8dd` |
| `P1-04a-Practice-A-390.dc.html` | 15084 | `f2a9dac3f85db52593e332de939faf77836022ed4ecdf8ab0b33e5664b777299` |
| `P1-04b-Practice-B-1440.dc.html` | 17722 | `92e112fa2aa1b958604c8bd4154ead0559c7408313bf311af4bd99dae0883f77` |
| `P1-04b-Practice-B-390-notes.dc.html` | 15240 | `7c9e77c43e65138a86c7dc783d3ee13ef06e08188419f02aa6b407645d1bdb68` |
| `P1-04c-Practice-A-390-keyboard.dc.html` | 17534 | `cb8c210a009636818e12e0661073e0f7aa7d1fbee6777529f7f9ec957170dd73` |
| `P1-04d-Practice-A-390-drawer.dc.html` | 22811 | `c260f897c5b77abe75b9a9471290569b70f49baeb9e7d284b3f00fb614b3c645` |
| `P1-05-Assessment-1440.dc.html` | 16321 | `ee03b748efecdbec878d909df08b044f92065b6d0b8fadf53e568bea9dc8773f` |
| `P1-05-Assessment-390.dc.html` | 13360 | `bc3d60c029d793b6df04b398af5fefd12e526c4fc5f49c7a1dbc21091607d73d` |
| `P1-06-Scenario-1440.dc.html` | 16034 | `257274b026ad48fcb6b4ecd3528f9296960f57790ce21196b9af40f4b36cde1b` |
| `P1-06-Scenario-390.dc.html` | 9631 | `198dcdfa12f7e5c858e3541f6af403f9e3087bf223ec18c721d2573d74853ec3` |
| `P1-07a-Growth-1440.dc.html` | 26737 | `7148cbdd5a58d31c12bda255a8476de45702d96f849c1330e1173b80860d46ba` |
| `P1-07a-Growth-390.dc.html` | 19516 | `ee4d3996f0e4ddb72c9c41f7594fff3ccc15f759bc31d869c52dd0797aedf2fe` |
| `P1-07b-Growth-empty-1440.dc.html` | 25838 | `9bbf08bc782f8625406c399c3e2f6cb9229e6e26960328a5bed95b9712b49aa2` |
| `P1-07b-Growth-empty-390.dc.html` | 6784 | `b502e0d4bfcd10a6d3bdc8a8d9ba5b0bc476a587c2a4ee93aee13062a8b777d8` |
| `P1-08-Reset-1440.dc.html` | 26416 | `aa4db4bd78fafdd98a4ae29a29ae80b4ab6c5a8f78bcca3438e83435a51aa8ad` |
| `P1-08-Reset-390.dc.html` | 7295 | `bca16443dc433b49040451132202e18630a4fcc5885ce5c971f266132c3c26eb` |
| `P1-B-Identity.dc.html` | 61009 | `109e2429d224671ec1c3546a8957f53a85d99e32a0d57cbbc9ba425e1913e71a` |
| `P1-C-Rules.dc.html` | 15686 | `cd3a819448b226a08d04abfa805cbc04ad6fcc20f3c0907571edf30264d52e9f` |
| `P1-D-Tokens.dc.html` | 87381 | `a8db0318ff15bb92d6ec7ccb488fedfa8013cf56ebe6edf8b6d94860cf28600d` |
| `P1-E-Behaviour.dc.html` | 54423 | `d9d1652b622393e63223407b23d414ee3d7c53b001805f13fd8f9c44b7d56176` |
| `P1-F-Controls.dc.html` | 36935 | `d69c15da1f698c802e3fddae1b0b5cfc92ea3ee22255c00d446e22a61f3e1af9` |
| `P2-AR-01-FlightDeck-1440.dc.html` | 29570 | `41e52c40ae0726d6236d8efb01f0ea71c78a851f1dae1f6b2135dbf45b7fa6aa` |
| `P2-AR-01-FlightDeck-390.dc.html` | 26758 | `3098c6a9862cc4cdcf145cd6bccd4aca233cd352e10bf1491d8d86c49c55195c` |
| `P2-AR-02-Learning-1440.dc.html` | 15833 | `2a8ef776ab34e35fe04754d9570814a53c1603bc3de5dda752ff8d00a5cc5944` |
| `P2-AR-02-Learning-390.dc.html` | 12567 | `8ae463f292b71098d068a8f9a461f00a71d8b8662f7a0efbf2b22be97b4697f0` |
| `P2-AR-03-Ghost-1440.dc.html` | 20991 | `c23c6ab9f2d15fc4a69ad510352d90d2a4daf6f120ced034ce323068714a9d23` |
| `P2-AR-03-Ghost-390.dc.html` | 14513 | `525b96912e6f6f7cd8742ff13bbfb95255eaeab623699b6eaeeb408dbebd38ef` |
| `P2-AR-04a-Practice-A-1440.dc.html` | 26344 | `d699dd614582750c2c30cf668deb23a7f768085aeaf0a33bc5aeaf724ed1e467` |
| `P2-AR-04a-Practice-A-390.dc.html` | 15364 | `e156f623ffd1117f91781a7b3697e05afff444c25b38f918ebb653051e0a3462` |
| `P2-AR-04b-Practice-B-1440.dc.html` | 18290 | `9642ab057d76f93fe74a148721b379a94c1c49bce16c107233ce8ee7401eee09` |
| `P2-AR-04b-Practice-B-390-notes.dc.html` | 15713 | `0a98c5b414e748766213a07d7691ce822a9b0c49adf55bc717dc90321f11ae98` |
| `P2-AR-04c-Practice-A-390-keyboard.dc.html` | 17975 | `5ceb7ba696ccbe4c8e5b46541757f49acb83ed9f0f74ff9fb7bda65e3551fa63` |
| `P2-AR-04d-Practice-A-390-drawer.dc.html` | 23481 | `3d3d1a648c25596b90dfb92e75dd539e937cd8b955469ace8e47e6f04875ff91` |
| `P2-AR-05-Assessment-1440.dc.html` | 16884 | `bdd0b72a3fd22c04a19cb83c4f38fb4849fe58b20904a91b049a6f7d19581a46` |
| `P2-AR-05-Assessment-390.dc.html` | 13773 | `189364e68e6fbbf4a407414ff0bc5d84d9868aff05d5b521fe670ae8c6ab1720` |
| `P2-AR-06-Scenario-1440.dc.html` | 16811 | `a83c525437714e085ec7dcdb198451eb1743365a6e1b508debc10500a5ed6656` |
| `P2-AR-06-Scenario-390.dc.html` | 9957 | `b1a35bb3ee8098373052071c15ef4a7682b7d2de458714c8335ee3df14ed9379` |
| `P2-AR-07a-Growth-1440.dc.html` | 27824 | `3faddd69077a713bee6d3e39036f580098fbb4e0caa80473286cb279bb4ef571` |
| `P2-AR-07a-Growth-390.dc.html` | 20185 | `4665a058e744b83863469da200b14c32a6895a9ad22fe9d5b7c17d8faa29f355` |
| `P2-AR-07b-Growth-empty-1440.dc.html` | 26841 | `6b3f32c0244efb37cb15b2d7d9e7f9dee4a75814ec6334f10022ce87f4849e7c` |
| `P2-AR-07b-Growth-empty-390.dc.html` | 7007 | `d4939293720328b61337a8739d4ca30ff857e6d68a2df66b67b43424547279b3` |
| `P2-AR-08-Reset-1440.dc.html` | 27461 | `7af2e7c90a04db05020df56be5fc4f70579ad5c0e7593f61bc29dd958f2974c4` |
| `P2-AR-08-Reset-390.dc.html` | 7553 | `97ecd983736de95319096b731a9fa34b23794213c7b27f9b62743ad41b3c850e` |
| `P2-BP-FlightDeck-1024-AR.dc.html` | 29826 | `7a61158041b097729c40cdc559f9c5b3e06a5d47829dc575010127e53faa9292` |
| `P2-BP-FlightDeck-1024-EN.dc.html` | 28573 | `b9ae09c0c0536f4ec287022b5100f043c28366adcf96f70f400d2518931137c8` |
| `P2-BP-FlightDeck-1280-EN.dc.html` | 28319 | `5bafdf66261628f432b43e2d67b86f9ddce98f98346b3aefcc64092232acb60c` |
| `P2-BP-FlightDeck-320-AR.dc.html` | 26758 | `34308dce110e86e99e43f3a394c58367dfc0723e01244f5abed6b848bb1f5328` |
| `P2-BP-FlightDeck-320-EN.dc.html` | 25671 | `01bdfae6c6c8c453f63e6e8bd4bda8047a7d5594058776ed49cdd3541e014f68` |
| `P2-BP-FlightDeck-360-EN.dc.html` | 25671 | `18002be4c24abb3a41096697aeac90e868971307bef481da47d7234af3784767` |
| `P2-BP-FlightDeck-430-EN.dc.html` | 25671 | `7bf716ec14b3394f548d9f3822855f7f13cc83013f115d0a1afa7c440d132ce7` |
| `P2-BP-FlightDeck-768-EN.dc.html` | 25462 | `7c00e1658c9e662966c4792e194c28a6889fe3f1a7630c6676e3a108956c35c4` |
| `P2-BP-Practice-A-1024-AR.dc.html` | 24940 | `fef2c2933d619b055ed1517607e269d306b8ecaedbdf67b21e29c9d2b9c808e9` |
| `P2-BP-Practice-A-1024-EN.dc.html` | 24976 | `4c2d76c11ea713c6d0dcab1be391bae1f2bc25da430c4b473c3d7e3702f940f1` |
| `P2-BP-Practice-A-1280-EN.dc.html` | 25845 | `99c09c823190600a4d46c79bc1707dae7af26a29c67ec8eed25daa1a51b5def3` |
| `P2-BP-Practice-A-320-AR.dc.html` | 15401 | `6b55113b0f028171857655d79ef97af70c5b875f65af73a5e839812185487460` |
| `P2-BP-Practice-A-320-EN.dc.html` | 15123 | `a4dd70c08fcb8ca99d06b3ca4490b1e12e8467c9a9aa263bf80c25ba4ccfdbc6` |
| `P2-BP-Practice-A-360-EN.dc.html` | 15086 | `c317657f84ed78293718106e1e9fc91ccef169a89be30dc2e6480d405a880210` |
| `P2-BP-Practice-A-430-EN.dc.html` | 15086 | `071d5d276de463bb3bf861fe5c26ff11ace10e65ecd2414902a0bb5ae976ee92` |
| `P2-BP-Practice-A-768-EN.dc.html` | 19792 | `f0ab36a6c33d258485c85e5a9840ce9bdafc4b67f60a052205064d6c900783d1` |
| `P2-Issues.dc.html` | 109101 | `ca2fbdb4e600024fe6b459123fcad587b25d59de5007957e24b70ad651ac4f3b` |
| `P2-Menu-390-AR.dc.html` | 20872 | `9b4bc62597db0ea43faf1eecb6516ec356c6cf5654de6271b79e76aa6646b9b3` |
| `P2-Menu-390-EN.dc.html` | 20418 | `f4e6ff7d1a59abf39f4552e6c741eb7243867dc7e83fef1f9078c19fe79228ce` |
