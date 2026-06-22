# 📱 Desenvolvimento Mobile

## 📝 Descrição do Projeto/Atividade
App para o monitoramento do sensor

---

## 🧠 Reflexão de Aprendizado

### 1. O que aprendi?
conectar em outros aparelhos, na web tambem, e dar mais comandos pelo terminal

---

## 🛠️ Tecnologias e Ferramentas Utilizadas
*   React Native / Expo
*   TypeScript
*   [Outra biblioteca, ex: Axios, React Navigation, React Native Vector Icons]

---

## 💻 layalt
import { Tabs } from 'expo-router';

export default function TabLayout() {
  return (
    <Tabs screenOptions={{ headerShown: false }}>
      <Tabs.Screen
        name="index"
        options={{ title: 'Início' }}
      />

      <Tabs.Screen
        name="plantas"
        options={{ title: 'Plantas' }}
      />

      <Tabs.Screen
        name="alertas"
        options={{ title: 'Alertas' }}
      />

      <Tabs.Screen
        name="perfil"
        options={{ title: 'Perfil' }}
      />
    </Tabs>
  );
}



