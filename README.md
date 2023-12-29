# Example function to extract vertices from an OBJ file
def extract_vertices_from_obj(obj_file_path):
    vertices = []

    with open(obj_file_path, 'r') as obj_file:
        for line in obj_file:
            if line.startswith('v '):
                # Split the line and extract x, y, z coordinates
                parts = line.split()
                x, y, z = float(parts[1]), float(parts[2]), float(parts[3])
                vertices.append([x, y, z])  # Append each vertex as a list

    return vertices

# Example usage:
obj_file_path = 'path/to/your/model.obj'
vertices = extract_vertices_from_obj(obj_file_path)
print(vertices)
