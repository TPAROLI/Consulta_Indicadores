from graphviz import Digraph

# Criando o organograma
org = Digraph("OrganogramaEquipe", format='png')
org.attr(rankdir='TB', size='10', fontname='Helvetica')

# Título
org.attr(label='📊 Organograma da Equipe', labelloc='t', fontsize='20')

# Turno Manhã
org.node('manha', '☀️ Turno Manhã\nSuporte: Thiago Rodrigues', shape='box', style='filled', fillcolor='lightyellow')
org.node('manha_n1', 'Nível 1', shape='box', style='filled', fillcolor='lightgrey')
org.node('manha_n2', 'Nível 2', shape='box', style='filled', fillcolor='lightgrey')

org.edge('manha', 'manha_n1')
org.edge('manha', 'manha_n2')

manha_n1_pessoas = [
    "Djalmir Sena", "Kelson Ricardo", "Fabio Almeida", "Ketlin Maciele",
    "Izabela Carneiro", "Leandro dos Santos", "Vaga a receber"
]
for i, nome in enumerate(manha_n1_pessoas):
    node_id = f"manha_n1_{i}"
    org.node(node_id, nome)
    org.edge('manha_n1', node_id)

manha_n2_pessoas = ["Carlos Alexandre", "Bruno Ribeiro"]
for i, nome in enumerate(manha_n2_pessoas):
    node_id = f"manha_n2_{i}"
    org.node(node_id, nome)
    org.edge('manha_n2', node_id)

# Turno Tarde
org.node('tarde', '🌙 Turno Tarde\nSuporte: Ulysses Ferreira', shape='box', style='filled', fillcolor='lightblue')
org.node('tarde_n1', 'Nível 1', shape='box', style='filled', fillcolor='lightgrey')
org.node('tarde_n2', 'Nível 2', shape='box', style='filled', fillcolor='lightgrey')

org.edge('tarde', 'tarde_n1')
org.edge('tarde', 'tarde_n2')

tarde_n1_pessoas = [
    "Guilherme Scalon", "Yan Ribeiro", "Romulo Nicolae", "Helliton Silva",
    "João Gabriel", "Rosemary Arruda", "Eduardo Pontes"
]
for i, nome in enumerate(tarde_n1_pessoas):
    node_id = f"tarde_n1_{i}"
    org.node(node_id, nome)
    org.edge('tarde_n1', node_id)

tarde_n2_pessoas = ["Brenda Fernanda", "Layssa Mendes"]
for i, nome in enumerate(tarde_n2_pessoas):
    node_id = f"tarde_n2_{i}"
    org.node(node_id, nome)
    org.edge('tarde_n2', node_id)

# Gerar a imagem
org.render('organograma_equipe', cleanup=True)
