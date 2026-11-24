# Resumen de métricas: Exploración 4 (METU, grieta / sin grieta)

Generado automáticamente. Muestra de METU: 2000 train, 500 validación, 1000 test (balanceado). Entrada: 64×64 gris. Referencia: azar 0.50.

## 1. Métricas principales en test (modelo de la primera semilla)

| modelo | test_acc | test_acc_IC95 | sensibilidad | especificidad | precision_grieta | test_f1_macro | roc_auc | kappa | mcc | pseudo_R2_McFadden | ECE | params | tiempo_s |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Regresión logística | 0.883 | [0.864, 0.902] | 0.794 | 0.972 | 0.966 | 0.882 | 0.898 | 0.766 | 0.778 | 0.396 | 0.039 | 4097 | 13.959 |
| RF · GridSearchCV | 0.970 | [0.959, 0.980] | 0.966 | 0.974 | 0.974 | 0.970 | 0.996 | 0.940 | 0.940 | 0.807 | 0.070 | 11818 | 236.514 |
| RF · RandomizedSearchCV | 0.970 | [0.959, 0.980] | 0.966 | 0.974 | 0.974 | 0.970 | 0.996 | 0.940 | 0.940 | 0.807 | 0.070 | 11818 | 98.292 |
| RF · BayesSearchCV | 0.974 | [0.963, 0.983] | 0.960 | 0.988 | 0.988 | 0.974 | 0.998 | 0.948 | 0.948 | 0.830 | 0.067 | 8906 | 157.829 |
| RF · Algoritmo Genético | 0.968 | [0.956, 0.978] | 0.948 | 0.988 | 0.988 | 0.968 | 0.997 | 0.936 | 0.937 | 0.808 | 0.069 | 4173 | 126.970 |
| MLP base | 0.881 | [0.860, 0.899] | 0.838 | 0.924 | 0.917 | 0.881 | 0.941 | 0.762 | 0.765 | 0.564 | 0.037 | 1081986 | 10.895 |
| MLP · Random Search | 0.933 | [0.916, 0.947] | 0.884 | 0.982 | 0.980 | 0.933 | 0.978 | 0.866 | 0.870 | 0.729 | 0.025 | 2100738 | 9.609 |
| MLP · Bayesiana | 0.945 | [0.930, 0.958] | 0.922 | 0.968 | 0.966 | 0.945 | 0.982 | 0.890 | 0.891 | 0.772 | 0.020 | 1050370 | 8.180 |
| MLP · Algoritmo Genético | 0.969 | [0.958, 0.979] | 0.954 | 0.984 | 0.984 | 0.969 | 0.994 | 0.938 | 0.938 | 0.827 | 0.049 | 1066690 | 8.041 |
| CNN desde cero | 0.997 | [0.993, 1.000] | 0.994 | 1.000 | 1.000 | 0.997 | 1.000 | 0.994 | 0.994 | 0.981 | 0.007 | 72594 | 32.020 |

## 2. Robustez: media y desviación entre semillas

| modelo | test_acc media | test_acc desv | test_F1 media | test_F1 desv |
|---|---|---|---|---|
| Regresión logística | 0.883 | nan | 0.882 | nan |
| RF · GridSearchCV | 0.970 | nan | 0.970 | nan |
| RF · RandomizedSearchCV | 0.970 | nan | 0.970 | nan |
| RF · BayesSearchCV | 0.974 | nan | 0.974 | nan |
| RF · Algoritmo Genético | 0.968 | nan | 0.968 | nan |
| MLP base | 0.900 | 0.017 | 0.900 | 0.017 |
| MLP · Random Search | 0.941 | 0.007 | 0.941 | 0.007 |
| MLP · Bayesiana | 0.946 | 0.004 | 0.946 | 0.004 |
| MLP · Algoritmo Genético | 0.965 | 0.004 | 0.965 | 0.004 |
| CNN desde cero | 0.997 | 0.002 | 0.997 | 0.002 |

## 3. Overfitting

| modelo | train_acc | val_acc | test_acc | brecha_acc_train_val | brecha_acc_train_test | train_log_loss | val_log_loss | brecha_log_loss_val_train | epocas_corridas | epoca_mejor | ratio_val_loss_final_min |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Regresión logística | 0.977 | 0.872 | 0.883 | 0.105 | 0.094 | 0.123 | 0.402 | 0.279 | nan | nan | nan |
| RF · GridSearchCV | 0.999 | 0.966 | 0.970 | 0.033 | 0.029 | 0.045 | 0.147 | 0.102 | nan | nan | nan |
| RF · RandomizedSearchCV | 0.999 | 0.966 | 0.970 | 0.033 | 0.029 | 0.045 | 0.147 | 0.102 | nan | nan | nan |
| RF · BayesSearchCV | 0.998 | 0.968 | 0.974 | 0.030 | 0.024 | 0.049 | 0.130 | 0.080 | nan | nan | nan |
| RF · Algoritmo Genético | 0.991 | 0.964 | 0.968 | 0.027 | 0.023 | 0.067 | 0.140 | 0.073 | nan | nan | nan |
| MLP base | 0.974 | 0.896 | 0.881 | 0.078 | 0.093 | 0.139 | 0.316 | 0.177 | 19.000 | 11.000 | 1.297 |
| MLP · Random Search | 0.989 | 0.942 | 0.933 | 0.047 | 0.056 | 0.039 | 0.182 | 0.143 | 22.000 | 14.000 | 1.936 |
| MLP · Bayesiana | 0.989 | 0.940 | 0.945 | 0.049 | 0.044 | 0.074 | 0.183 | 0.109 | 21.000 | 13.000 | 1.000 |
| MLP · Algoritmo Genético | 0.990 | 0.946 | 0.969 | 0.044 | 0.021 | 0.080 | 0.157 | 0.077 | 14.000 | 6.000 | 1.072 |
| CNN desde cero | 1.000 | 1.000 | 0.997 | -0.000 | 0.003 | 0.007 | 0.006 | -0.001 | 20.000 | 14.000 | 1.603 |

## 4. Random Forest: tres buscadores

| método | evaluaciones | mejor_cv_acc | tiempo_s | mejores_hiperparámetros | test_acc |
|---|---|---|---|---|---|
| GridSearchCV | 32 | 0.968 | 236.514 | {'criterion': 'gini', 'max_depth': 20, 'n_estimators': 100} | 0.970 |
| RandomizedSearchCV | 15 | 0.968 | 98.292 | {'n_estimators': 100, 'max_depth': 20, 'criterion': 'gini'} | 0.970 |
| BayesSearchCV | 15 | 0.966 | 157.829 | {'criterion': 'entropy', 'max_depth': 20, 'n_estimators': 100} | 0.974 |
| Algoritmo Genético | 15 | 0.962 | 126.970 | {'n_estimators': 53, 'max_depth': 16, 'criterion': 'entropy'} | 0.968 |

## 5. MLP: optimizador × learning rate (mejor val_acc)

| optimizador | 0.0001 | 0.001 | 0.01 | 0.1 |
|---|---|---|---|---|
| Adam | 0.918 | 0.910 | 0.742 | 0.500 |
| Nadam | 0.912 | 0.916 | 0.744 | 0.500 |
| RMSprop | 0.914 | 0.908 | 0.756 | 0.702 |
| SGD | 0.788 | 0.842 | 0.944 | 0.902 |
| SGD + momentum | 0.840 | 0.936 | 0.924 | 0.740 |

## 6. MLP: convergencia con el mejor lr (3 semillas)

| optimizador | lr | mejor_val_acc | epocas_hasta_meta |
|---|---|---|---|
| SGD | 0.010 | 0.929 | 17.667 |
| SGD + momentum | 0.001 | 0.931 | 17.667 |
| RMSprop | 0.000 | 0.910 | 28.000 |
| Adam | 0.000 | 0.907 | 34.000 |
| Nadam | 0.001 | 0.917 | 25.667 |

## 7. Regularización (train reducido, sin parada temprana)

| regularización | train_acc | val_acc | test_acc | brecha_train_val |
|---|---|---|---|---|
| Sin regularización | 0.985 | 0.820 | 0.830 | 0.165 |
| L2 (1e-3) | 0.997 | 0.837 | 0.837 | 0.160 |
| Dropout (0.5) | 0.962 | 0.831 | 0.840 | 0.131 |
| BatchNorm | 0.975 | 0.847 | 0.861 | 0.128 |
| L2 + Dropout + BN | 0.981 | 0.856 | 0.878 | 0.125 |

## 8. Buscadores de la MLP (mismo presupuesto)

| método | evaluaciones | mejor_val_acc | media_val_acc | evals_hasta_99% | tiempo_min |
|---|---|---|---|---|---|
| Random Search | 15 | 0.946 | 0.895 | 1 | 2.679 |
| Bayesiana | 15 | 0.942 | 0.905 | 2 | 3.737 |
| Algoritmo Genético | 15 | 0.948 | 0.924 | 4 | 2.631 |

MLP elegida por validación: **MLP · Algoritmo Genético** `{'n_capas': 2, 'units_0': 256, 'units_1': 64, 'dropout': 0.2, 'l2': 0.0001, 'batchnorm': True, 'learning_rate': 0.002335963502626158, 'optimizador': 'sgd_momentum'}`

## 9. CNN: optimizador × learning rate (mejor val_acc)

| optimizador | 0.0001 | 0.001 | 0.01 |
|---|---|---|---|
| Adam | 0.992 | 0.996 | 0.998 |
| Nadam | 0.992 | 0.998 | 0.998 |
| RMSprop | 0.992 | 1.000 | 0.986 |
| SGD | 0.914 | 0.974 | 0.988 |
| SGD + momentum | 0.976 | 0.986 | 0.996 |

## 10. Curva de aprendizaje (accuracy en test)

| n_por_clase | Regresión logística | Random Forest | MLP base | MLP · Algoritmo Genético (elegida) | CNN desde cero |
|---|---|---|---|---|---|
| 50.000 | 0.786 | 0.759 | 0.781 | 0.931 | 0.857 |
| 100.000 | 0.840 | 0.913 | 0.834 | 0.948 | 0.993 |
| 250.000 | 0.868 | 0.952 | 0.861 | 0.953 | 0.995 |
| 500.000 | 0.860 | 0.969 | 0.875 | 0.963 | 0.997 |
| 1000.000 | 0.883 | 0.970 | 0.900 | 0.965 | 0.996 |

## 11. Contraste con PHI-Net (binario, fotos de campo)

| modelo | METU_accuracy | accuracy | balanced_acc | sensibilidad | especificidad | roc_auc | balanced_acc_desv |
|---|---|---|---|---|---|---|---|
| Siempre 'con daño' | nan | 0.563 | 0.500 | 1.000 | 0.000 | 0.500 | 0.000 |
| Regresión logística | 0.883 | 0.555 | 0.553 | 0.567 | 0.540 | 0.583 | 0.000 |
| MLP · Algoritmo Genético | 0.965 | 0.621 | 0.616 | 0.651 | 0.581 | 0.658 | 0.015 |
| CNN desde cero | 0.997 | 0.733 | 0.721 | 0.816 | 0.626 | 0.803 | 0.033 |

## Tiempos (min)

| etapa | min |
|---|---|
| metu_muestra | 0.3 |
| logreg | 0.2 |
| rf_gridsearchcv | 3.9 |
| rf_randomizedsearchcv | 1.6 |
| rf_bayessearchcv | 2.6 |
| rf_algoritmo_genetico | 2.1 |
| MLP base | 0.8 |
| barrido_mlp | 3.9 |
| convergencia_mlp | 4.5 |
| regularizacion | 1.9 |
| busq_random | 2.7 |
| busq_bayesiana | 3.7 |
| busq_ga_pygad | 2.6 |
| barrido_cnn | 7.8 |
| CNN final | 1.7 |
| curva_pasos_mlp_algoritmo_genetico_rmsprop_0.001_s3 | 17.9 |
| phinet_mlp_algoritmo_genetico_rmsprop_0.001_s3 | 4.3 |
