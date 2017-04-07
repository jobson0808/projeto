# projeto
projeta da sala de aula
import javax.print.attribute.standard.MediaSize.Other;

public class Vertce {
	private final int id;
	
	public Vertce (int id) {
		this.id= id;
	}

	public int getid() {
		return id;
	}
	
	public int hashCode(){
		final int prime = 31;
		int result = 1;
		result = prime * result + id;
		return result;
	}
	public boolean equais (Object obj){
		if (this == obj)
			return true;
		if (obj == null)
			return false;
		if (getClass() != obj.getClass())
			return false;
		Vertce other = (Vertce) obj;
		if (id != other.id)
			return false;
		return true;
	}
}

public class Aresta {
	
	private final Vertce v1;
	private final Vertce v2;
	
	public Aresta (Vertce v1, Vertce v2){
		super();
		this.v1 = v1;
		this.v2 = v2;
	}
	public Vertce getv1(){
		return v1;
	}
	public Vertce getv2(){
		return v2;
	}

}



import java.util.ArrayList;
import java.util.HashMap;
import java.util.HashSet;
import java.util.LinkedList;
import java.util.List;
import java.util.Map;
import java.util.Queue;
import java.util.Set;

public class BFS {
	
	private final List<Aresta>arestas;
	private Map<Vertce, Vertce> predecessores;
	private Set<Vertce> visitados;
	private Queue<Vertce> fila;
	
	public BFS (List<Aresta> arestas){
		this.arestas= arestas;
	}
	
	public void executar(Vertce inicial){
		predecessores = new HashMap<Vertce, Vertce>();
		visitados = new HashSet<Vertce>();
		fila = new LinkedList<Vertce>();
		
		if (inicial == null){
			return;
		}
		 fila.add(inicial);
		 predecessores.put(inicial, null);
		 
		 while (!fila.isEmpty()){
			 Vertce v = fila.poll();
			 visitados.add(v);
			 
			for (Vertce w : getVizinhos(v)){
				if (!visitados.contains(w)){
					fila.add(w);
					predecessores.put(w, v);
				}
			}
		 }
	
	}
	private List<Vertce> getVizinhos(Vertce node){
		List<Vertce> vizinhos = new ArrayList<Vertce>();
		for(Aresta aresta : arestas){
			if (aresta.getv1().equais(node)){
				vizinhos.add(aresta.getv2());
			}else if (aresta.getv2().equais(node)){
				vizinhos.add(aresta.getv1());
			}
			
		}
		return vizinhos;
	}

	public LinkeList<Vertce>getCaminho(Vertce alvo){
		LinkedList<Vertce>
		
	}
	
}


